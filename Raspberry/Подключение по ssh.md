##### Просмотр IP Raspberry через wnetwatcher
1. Открыть приложение
2. Дождаться пока в списке появится устройство под названием `raspberrypi`
3. Слева будет его IP

##### Подключение через PuTTY
1. Открыть приложение
2. Вбить в консоль `ip_raspberry`/`raspberrypi.local`
3. Обновить пакеты `sudo apt-get update && sudo apt-get upgrade -y`
4. Открыть настройки `sudo raspi-config`
5. Включить VNC `Interface option -> VNC`

##### Увеличить скорость Wi-Fi
Ввести в консоль
```
iw list
iw reg set US
```

##### Если Wi-Fi часто сам отключается
`sudo iw dev wlan0 set power_save off`

##### Подключение к Wi-Fi через ноутбук
1. Создать файл под названием `wpa_supplicant.conf`
2. Вставить внутрь следующую информацию, заменив название и пароль сети
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
            ssid="Название Wi-Fi"
            psk="Пароль"
            key_mgmt=WPA-PSK
}	
```
