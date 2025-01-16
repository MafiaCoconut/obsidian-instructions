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
#### Отправка изменений на сервер из папки проекта
```zsh
git push --recurce-submodules=<status>
```
`--recurce-submodules=check` - Перед отправкой папки проекта проверит отправлены ли изменение в папках модулей
`--recurce-submodules=on-demand` - Перед отправкой папки проекта сам отправит последние изменений модулей на сервер

##### Команда конфигурации значения --recurce-submodules по умолчанию  
```zsh
git config push.recurseSubmodules check
```

```zsh
git config push.recurseSubmodules on-demand
```

## Получение новой версии с сервера
#### Обновление модуля  в папке проекта
```zsh
git submodule update --remote <SubmoduleDir>
```

#### Обновление модуля в папке модуля
```zsh
git pull
```
 
## Настройка сокращений команд
```zsh
git config alias.sdiff '!'"git diff && git submodule foreach 'git diff'"
git config alias.spush 'push --recurse-submodules=on-demand'
git config alias.supdate 'submodule update --remote --merge'
```

## Удаление
```zsh
git submodule deinit -f <path>
git rm -f <path>
rm -rf .git/modules/<path>
```