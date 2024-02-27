#### Создание нового экземпляра билдера
```sh
docker buildx create --name mybuilder
```

#### Переключение на другой билдер
```sh
docker buildx use <name>
```

#### Список доступных билдеров
```sh
docker buildx ls
```