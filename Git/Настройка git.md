# Внесение своих параметров в git
## Глобальные настройки
```
git config --global user.name "username"
git config --global user.email "dadsdad@gmail.com"
```

## Локальные настройки
```
git config --local user.name "username"
git config --local user.email "dadsdad@gmail.com"
```

# Настройка локальных файлов

Raspberry:

Создание ssh ключа
`ssh-keygen -t rsa -b 4096 -C "dadsdad@gmail.com"

Вывод на экран ssh ключа
`cat ~/.ssh/id_rsa.pub`

Переход с url подключения на ssh
`git remote set-url origin git@github.com:username/sffafa.git


# Субмодули
```
Project/
|
- Subproject/
```

## Добавление нового модуля
```zsh
git submodele add <github-link>
```


## Клонирование

### Первое клонирование
```zsh
git clone <github-link>

git submodule init

git submodule update
```

OR

```zsh
git clone --recurce-submodules <github-link> 
```

OR

```zsh
git clone <github-link>

git submodule update --init --recursive
```

## Обновление проекта/модуля на сервере
#### Обновление модуля  в папке проекта
```zsh
git submodule update --remote <SubmoduleDir>
```

## Получение новой версии с сервера


