### Установка 
`pip install SQLAlchemy`

### Подготовка к запуску

Устанавливаем `pydantic-settings`

Создаём класс `DBSettings` в котором будем брать данные из `env` 
```python
class DBSettings(BaseSettings):  
    DB_HOST: str  
    DB_PORT: int  
    DB_USER: str  
    DB_PASSWORD: str  
    DB_NAME: str  
```

Внутри класса нам нужно создать функцию, которая будет возвращать адресс, по которому `SQLAlchemy` будет обращаться к БД
```python
# Функция для асинхронного подключения
@property  
def DATABASE_URL_asyncpg(self):  
    return f"postgresql+asyncpg://{self.DB_USER}:{self.DB_PASSWORD}@{self.DB_HOST}:{self.DB_PORT}/{self.DB_NAME}"  

# Функция для синхронного подключения
@property  
def DATABASE_URL_psycopg(self):  
    return f"postgresql+psycopg://{self.DB_USER}:{self.DB_PASSWORD}@{self.DB_HOST}:{self.DB_PORT}/{self.DB_NAME}"
```

Также внутри  класса нужно создать переменную `model_config`, которая инициализирует класс `SettingsConfigDict`, чтобы брать данные из конкретного файла env и указать, что все остальные env переменные нужно игнорировать
```python
model_config = SettingsConfigDict(env_file="../.env", extra="ignore")
```


### Создание engine

После инициализации класса `DBSettings` нужно создать engine
#### Синхронный движок
```python
sync_engine = create_engine(  
    url=db_settings.DATABASE_URL_psycopg,  
    echo=True, # Выводит подробные логи в консоль
    pool_size=10,  
    max_overflow=20,  
    pool_timeout=30,  
    pool_recycle=1800,  
    pool_pre_ping=True,  
)  
```


#### Асинхронный движок
```python
async_engine = create_async_engine(  
    url=db_settings.DATABASE_URL_asyncpg,  
    echo=True,  # Выводит подробные логи в консоль
    pool_size=10,  
    max_overflow=20,  
    pool_timeout=30,  
    pool_recycle=1800,  
    pool_pre_ping=True,  
)
```

#### Модели
Для обращения к базе данных через `SQLAlchemy` можно использовать модели баз данных

Для этого создаём базовый класс, от которого будем наследовать модели баз данных
```python
from sqlalchemy.orm import DeclarativeBase

class Base(DeclarativeBase):  
    pass
```

При создании модели базы данных нужно наследовать её от `Base`
Также нужно создать переменную `__tablename__` в которую записать название вашей базы данных
```python
from sqlalchemy.orm import Mapped, mapped_column
from sqlalchemy import BigInteger

class UserOrm(Base):  
    __tablename__ = 'users'  
  
    user_id: Mapped[int] = mapped_column(BigInteger, primary_key=True)  
    username: Mapped[str]  
    mailing_time: Mapped[str]  
    language: Mapped[str]  
    canteen_id: Mapped[int]  
    status: Mapped[str] = mapped_column(default="active")
    #updated_at: Mapped[updated_at] 
    #created_at: Mapped[created_at]  
    
```
`Mapped` отвечает за указание на тип данных, которые должны быть в этом столбце
`mapped_column` расширяет информацию о столбце. 
###### Параметры `mapped_column`
- `default` - дефолтные данные, если данные не были указаны
- `primary_key` - указать, что столбец является ключевым
- `server_default` - данные запишутся на сервер в момент создания строки
- `onupdate` - действие, которое произойдёт с данными в момент обновления любых данных в строке


Также можно заранее заготовить часто используемые настройки столбоц и импортировать их в модель базы данных.
Сделаем пример настроек для `primary_key`, `created_at`, `updated_at`
```python
from datetime import datetime, UTC  
from typing import Annotated  
from sqlalchemy.orm import mapped_column  
from sqlalchemy import text  
  
intpk = Annotated[int, mapped_column(primary_key=True)]  
  
created_at = Annotated[datetime, mapped_column(server_default=text("TIMEZONE('utc', now())"))]  

updated_at = Annotated[datetime, mapped_column(  
    server_default=text("TIMEZONE('utc', now())"),  
    onupdate=lambda: datetime.now(UTC).replace(tzinfo=None),  
)]
```

