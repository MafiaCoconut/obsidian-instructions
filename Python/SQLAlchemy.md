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

