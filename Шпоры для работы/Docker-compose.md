# Docker-Compose Volumes

### Что такое Volumes в Docker-Compose?

Перевод: Способ хранения данных вне контейнеров, управляемых с помощью docker-compose.
- Eine Methode zur Speicherung von Daten außerhalb der Container, die mit docker-compose verwaltet werden.

### Зачем нужны Volumes в Docker-Compose?

Перевод: Позволяют сохранять данные независимо от жизненного цикла контейнеров в составе сервисов.
- Erlauben die Speicherung von Daten unabhängig vom Lebenszyklus der Container, die Teil von Diensten sind.

### Основные функции Volumes в Docker-Compose

- **Персистентность данных**: Данные сохраняются даже после удаления контейнеров.
  - Daten bleiben erhalten, selbst wenn die Container gelöscht werden.

- **Совместное использование данных**: Одни и те же данные могут использоваться несколькими контейнерами.
  - Dieselben Daten können von mehreren Containern verwendet werden.

- **Изоляция данных**: Обеспечивают изоляцию данных между хостом и контейнерами.
  - Gewährleisten die Isolation von Daten zwischen Host und Containern.

### Определение Volumes в docker-compose.yml

Перевод: Раздел для определения Volumes, используемых в сервисах.
- Abschnitt zur Definition von Volumes, die in Diensten verwendet werden.

services:
  web:
    image: nginx
    volumes:
      - myvolume:/app/data

volumes:
  myvolume:

### Создание и использование Volumes в сервисах

Перевод: Как указать Volume для использования в сервисе.
- Wie man ein Volume zur Verwendung in einem Dienst angibt.

services:
  db:
    image: mysql
    volumes:
      - dbdata:/var/lib/mysql

volumes:
  dbdata:

### Разделяемые и анонимные Volumes

Перевод: Определение разделяемых и анонимных Volumes.
- Definition von gemeinsamen und anonymen Volumes.

services:
  web:
    image: nginx
    volumes:
      - sharedvolume:/shared/data
      - /anonymous/data

volumes:
  sharedvolume:

### Просмотр Volumes с помощью docker-compose

Перевод: Команда для отображения всех Volumes, определенных в docker-compose.
- Ein Befehl zum Anzeigen aller Volumes, die in docker-compose definiert sind.

docker-compose volume ls

### Удаление Volumes с помощью docker-compose

Перевод: Команда для удаления Volumes, не используемых контейнерами.
- Ein Befehl zum Löschen von Volumes, die von keinen Containern verwendet werden.

docker-compose down -v



# Docker-Compose YAML

### version

Перевод: Определяет версию файла docker-compose.
- Gibt die Version der docker-compose-Datei an.

version: '3.8'

### services

Перевод: Определяет контейнеры, которые будут созданы.
- Definiert die Container, die erstellt werden sollen.
```
services:
  web:
    image: nginx
```

### image

Перевод: Указывает образ, который будет использоваться для создания контейнера.
- Gibt das Image an, das für die Erstellung des Containers verwendet wird.

```
services:
  web:
    image: nginx
```

### build

Перевод: Определяет параметры сборки для контейнера.
- Definiert Build-Parameter für den Container.

```
services:
  web:
    build: ./path

```
### command

Перевод: Определяет команду, которая будет выполнена при запуске контейнера.
- Gibt den Befehl an, der beim Start des Containers ausgeführt werden soll.

```
services:
  web:
    command: echo "Hello, World"
```

### environment

Перевод: Определяет переменные окружения для контейнера.
- Definiert Umgebungsvariablen für den Container.

```
services:
  web:
    environment:
      - DEBUG=1
```

### ports

Перевод: Определяет перенаправление портов между хостом и контейнером.
- Definiert Portweiterleitungen zwischen Host und Container.

```
services:
  web:
    ports:
      - "8080:80"
```

### volumes

Перевод: Определяет тома, которые будут подключены к контейнеру.
- Definiert Volumes, die an den Container angehängt werden sollen.

```
services:
  web:
    volumes:
      - ./data:/var/www/html
```

### networks

Перевод: Определяет сети, к которым будет подключен контейнер.
- Definiert Netzwerke, mit denen der Container verbunden wird.

```
services:
  web:
    networks:
      - my-network
```

### depends_on

Перевод: Указывает на зависимости от других сервисов.
- Gibt Abhängigkeiten von anderen Diensten an.

```
services:
  web:
    depends_on:
      - db
```

### restart

Перевод: Определяет политику перезапуска контейнера.
- Definiert die Neustart-Politik des Containers.

```
services:
  web:
    restart: always
```

### deploy

Перевод: Определяет параметры развертывания для Docker Swarm.
- Definiert Bereitstellungsparameter für Docker Swarm.

```
services:
  web:
    deploy:
      replicas: 3
```

### secrets

Перевод: Определяет секреты, которые будут использованы контейнером.
- Definiert Geheimnisse, die vom Container verwendet werden.

```
services:
  web:
    secrets:
      - my_secret
```

### configs

Перевод: Определяет конфигурации, которые будут использованы контейнером.
- Definiert Konfigurationen, die vom Container verwendet werden.

```
services:
  web:
    configs:
      - my_config

```