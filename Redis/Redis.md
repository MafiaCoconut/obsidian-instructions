## Установка
### Ubuntu
```bash
sudo apt-get install redis
```

###### Запуск
```bash
sudo systemctl start redis
```

###### Остановка
```bash
sudo systemctl stop redis
```

## Подключение через консоль
```bash
redis-cli
```

## Команды 
SET <ключ><значение> - установить ключ
SET <ключ><значение> EX <время в секундах> - установить ключ c TTL

GET <ключ> - получить ключ


TTL - узнать сколько осталось времени жить ключу

DEL <ключ> - удалить ключ