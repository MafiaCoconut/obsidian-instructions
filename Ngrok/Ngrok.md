## Запуск
### Консоль
```sh
ngrok http --domain=ibex-smart-smoothly.ngrok-free.app 8080
```

###  Docker
```sh
docker run -it -e NGROK_AUTHTOKEN=2jwJP1lzjnmQBtfXhWWe0s6cqxk_44bXjBnFZXYKbke39Rjss ngrok/ngrok http 8080 --domain=ibex-smart-smoothly.ngrok-free.app

```

## Авторизация в консоли
```sh
ngrok config add-authtoken <TOKEN>
```