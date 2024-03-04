### Загрузка проекта на RaspberryPi

`git clone` 

-------------------------------------------------
## Создание venv

Создание venv
`python -m venv venv`

Запуск venv
`source venv/bin/activate`

установка библиотек 
`pip install -r requirements.txt`


## Создание автозапуска

Создать файл:
`nano названиe.service`

просмотр пути до активной папки - `pwd`
 
**На месте русских слов вставить название/описание проекта**

```
[Unit]
Description=Описание
After=multi-user.target

[Service]
type=simple
ExecStart=/home/pi/Projects/Репозиторий/venv/bin/python /home/pi/Projects/Репозиторий/app/main.py
WorkingDirectory=/home/pi/Projects/Репозиторий/
Restart=always

[Install]
WantedBy=multi-user.target
```

Сохранить и выйти
`ctrl + X`

Вставить
```
sudo cp название.service /etc/systemd/system
sudo systemctl enable название.service 
sudo systemctl restart название.service
```


## Удаление
Откройте терминал.

Остановить выполнение службы
`sudo systemctl stop <имя_службы>` 

Отключить автоматический запуск службы
`sudo systemctl disable <имя_службы>`

Удаление службы из директории
`sudo rm /etc/systemd/system/<имя_службы>` 

Обновление системы и удаление информации о службе
`sudo systemctl daemon-reload` 

*Примечание: Будьте осторожны при удалении службы, убедитесь, что вы удаляете правильную службу и она больше не нужна.*



