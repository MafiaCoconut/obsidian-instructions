## Список ключей

```terminal
ls -al ~/.ssh
```

## Создание ключа
### ed25519
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
#### Сохранение
`ssh-add ~/.ssh/id_ed25519`

### rsa
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
#### Сохранение
`ssh-add ~/.ssh/id_rsa`

## Вывести в терминал ключ
`cat ~/.ssh/id_ed25519.pub`