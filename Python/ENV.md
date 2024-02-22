### Установка
Скачиваем библиотеку
`pip install python-dotenv`

### Файл `.env`
Создаём файл `.env`

Внутри файла `.env` переменные записываются в формате
```
SECRET_KEY=123456789
SECRET_TOKEN=4124214_!@4124
```
Для хранения в одной переменной нескольких значений можно использовать запятую или пробел. А в коде использовать `.split(',')`
`ADMINS_ID=123,456,789`

### Использование в коде
```python
from dotenv import load_dotenv
import os

# Загрузка переменных окружения из файла .env
load_dotenv()

# Доступ к переменным окружения
secret_key = os.getenv('SECRET_KEY')
database_url = os.getenv('SECRET_TOKEN')
admins_id=os.getenv('ADMINS_ID').split(',')
print(secret_key)
print(database_url)
```