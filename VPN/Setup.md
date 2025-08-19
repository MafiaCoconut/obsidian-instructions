Оригинал
https://www.youtube.com/watch?v=zt4oxHeUbdk

##### 1 Connect to server with ssh

##### 2 Change ssh port
``` shell
sudo nano /etc/ssh/sshd_config
```
Find line \#Port 22, comment out, rewrite '22' to which you want \<port\>, save
```shell
systemctl daemon-reload
systemctl restart ssh
```

##### 3 Настраиваем Firewall
```
ufw enable && ufw allow <port>/tcp
```

##### 4 Убираем возможность пинговать сервер
```shell
nano /etc/ufw/before.rules
```

В открывшемся файле ищем INPUT и Forward и делаем чтобы выглядело точно также
```
# ok icmp codes for INPUT
-A ufw-before-input -p icmp --icmp-type destination-unreachable -j DROP
-A ufw-before-input -p icmp --icmp-type time-exceeded -j DROP
-A ufw-before-input -p icmp --icmp-type parameter-problem -j DROP
-A ufw-before-input -p icmp --icmp-type echo-request -j DROP
-A ufw-before-input -p icmp --icmp-type source-quench DROP
# ok icmp code for FORWARD
-A ufw-before-forward -p icmp --icmp-type destination-unreachable -j DROP
-A ufw-before-forward -p icmp --icmp-type time-exceeded -j DROP
-A ufw-before-forward -p icmp --icmp-type parameter-problem -j DROP
-A ufw-before-forward -p icmp --icmp-type echo-request -j DROP
```

```shell
ufw disable && ufw enable
```

##### 5 Установка 3x-ui
Переходим по ссылке https://github.com/MHSanaei/3x-ui и устанавливаем на сервере

После установки получаем 
Username: 
Password: 
Port: \<x-uiport>
WebBasePath: 
Access URL: 

```shell
ufw allow <x-uiport>/tcp
```

##### 6 Настройка простого VPN 
Переходим в Access URL, вводим данные, которые были в консоли до.