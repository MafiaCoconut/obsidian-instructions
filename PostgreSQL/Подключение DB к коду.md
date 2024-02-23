### Сначала создаём network
```sh
docker network create <name>
```

### Запуск `postgresql`
##### Скачиваем postgres
```sh
docker pull postgres
```

##### Запускаем контейнер
```sh
 docker run -d \
  -e POSTGRES_PASSWORD=admin \
  -e POSTGRES_USER=admin \
  -e POSTGRES_DB=test_db \
  --net=network_name \
  --name postgres_name \
  postgres
```

##### Создаём `table`
```sh
  CREATE TABLE users (
  users_id SERIAL PRIMARY KEY,
  telegram_id VARCHAR(100),
  telegram_username TEXT);
```

### Запуск кода
##### Dockerfile
```
FROM python:3.10  
  
WORKDIR /app  
  
COPY requirements.txt .  
  
RUN pip install --no-cache-dir -r requirements.txt  
  
COPY app/ .  
  
CMD ["python", "main.py"]
```
Примечание: весь код проекта должен находиться внутри папки `app`

##### Создаём образ
```sh
docker build -t name:tag path\to\dockerfile 
```

##### Запускаем контейнер кода
```sh
docker run \
  --name cube-backend \
  --env-file .env \
  -e DB_HOST=postgres_name \
  -p 8000:8000 \
  --net=network_name \
 name:tag
```
**ВАЖНО** 
1. DB_HOST - это имя postgres контейнера
2. --net должна быть одинаковой в обоих контейнерах
