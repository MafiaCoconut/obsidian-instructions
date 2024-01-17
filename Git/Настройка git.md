Внесение своих параметров в git
```
git config --global user.name "username"
git config --global user.email "dadsdad@gmail.com"
```

Raspberry:

Создание ssh ключа
`ssh-keygen -t rsa -b 4096 -C "dadsdad@gmail.com"

Вывод на экран ssh ключа
`cat ~/.ssh/id_rsa.pub

Переход с url подключения на ssh
`git remote set-url origin git@github.com:username/sffafa.git


