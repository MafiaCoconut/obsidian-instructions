## Основные команды (Grundlegende Befehle)

#### 1. **docker --version**
- **Показывает установленную версию Docker**
- Zeigt die installierte Docker-Version an
- Пример:
 ```bash
 docker --version
 ```

#### 2. **docker info**
- **Показывает общую информацию о Docker**
- Zeigt allgemeine Informationen über Docker an
- Пример:
 ```bash
 docker info
 ```

#### 3. **docker pull**
- **<font color="#00b050">Загружает</font> образ из Docker Hub или другого реестра**
- <font color="#00b050">Lädt</font> ein Image aus Docker Hub oder einem anderen Registry herunter
- Пример:
 ```bash
 docker pull ubuntu
 ```

#### 4. **docker build**
- **<font color="#00b050">Создает</font> образ из Dockerfile**
- <font color="#00b050">Erstellt</font> ein Image aus einer Dockerfile
- Пример:
 ```bash
 docker build -t myimage:latest .
 ```

#### 5. **docker run**
- **Запускает контейнер из образа**
- Startet einen Container aus einem Image
- Пример:
 ```bash
 docker run -d -p 80:80 myimage:latest
 ```

#### 6. **docker ps**
- **Показывает работающие контейнеры**
- Zeigt laufende Container an
- Пример:
 ```bash
 docker ps
 ```

#### 7. **docker ps -a**
- **Показывает все контейнеры, включая остановленные**
- Zeigt alle Container an, einschließlich der gestoppten
- Пример:
 ```bash
 docker ps -a
 ```

#### 8. **docker images**
- **Показывает локально сохраненные образы**
- Zeigt lokal gespeicherte Images an
- Пример:
 ```bash
 docker images
 ```

#### 9. **docker rm**
- **Удаляет один или несколько контейнеров**
- Löscht einen oder mehrere Container
- Пример:
 ```bash
 docker rm container_id
 docker rm $(docker ps -a -q)
 ```

#### 10. **docker rmi**
- **Удаляет один или несколько образов**
- Löscht ein oder mehrere Images
- Пример:
  ```bash
  docker rmi image_id
  docker rmi $(docker images -q)
  ```

#### 11. **docker stop**
- **Останавливает работающий контейнер**
- Stoppt einen laufenden Container
- Пример:
  ```bash
  docker stop container_id
  ```

#### 12. **docker start**
- **Запускает остановленный контейнер**
- Startet einen gestoppten Container
- Пример:
  ```bash
  docker start container_id
  ```

#### 13. **docker restart**
- **Перезапускает контейнер**
- Startet einen Container neu
- Пример:
  ```bash
  docker restart container_id
  ```

#### 14. **docker logs**
- **Показывает логи контейнера**
- Zeigt die Logs eines Containers an
- Пример:
  ```bash
  docker logs container_id
  ```

#### 15. **docker exec**
- **Выполняет команду внутри работающего контейнера**
- Führt einen Befehl innerhalb eines laufenden Containers aus
- Пример:
  ```bash
  docker exec -it container_id bash
  ```

#### 16. **docker network ls**
- **Показывает список сетей Docker**
- Zeigt die Liste der Docker-Netzwerke an
- Пример:
  ```bash
  docker network ls
  ```

#### 17. **docker network create**
- **Создает новую сеть Docker**
- Erstellt ein neues Docker-Netzwerk
- Пример:
  ```bash
  docker network create mynetwork
  ```

#### 18. **docker network connect**
- **Подключает контейнер к сети**
- Verbindet einen Container mit einem Netzwerk
- Пример:
  ```bash
  docker network connect mynetwork container_id
  ```

#### 19. **docker network disconnect**
- **Отключает контейнер от сети**
- Trennt einen Container von einem Netzwerk
- Пример:
  ```bash
  docker network disconnect mynetwork container_id
  ```

#### 20. **docker volume ls**
- **Показывает список томов Docker**
- Zeigt die Liste der Docker-Volumes an
- Пример:
  ```bash
  docker volume ls
  ```

#### 21. **docker volume create**
- **Создает новый том Docker**
- Erstellt ein neues Docker-Volume
- Пример:
  ```bash
  docker volume create myvolume
  ```

#### 22. **docker volume rm**
- **Удаляет том Docker**
- Löscht ein Docker-Volume
- Пример:
  ```bash
  docker volume rm myvolume
  ```

#### 23. **docker-compose up**
- **Запускает контейнеры, определенные в docker-compose.yml**
- Startet Container, die in der docker-compose.yml definiert sind
- Пример:
  ```bash
  docker-compose up
  ```

#### 24. **docker-compose down**
- **Останавливает и удаляет контейнеры, определенные в docker-compose.yml**
- Stoppt und entfernt Container, die in der docker-compose.yml definiert sind
- Пример:
  ```bash
  docker-compose down
  ```



## Основные инструкции Dockerfile (Grundlegende Dockerfile-Anweisungen)

#### FROM
- **Задает базовый образ для создания нового образа**
- Legt das Basis-Image fest, aus dem ein neues Image erstellt wird
- Пример:

	`FROM ubuntu:20.04`

#### LABEL
- **Добавляет метаданные к образу**
- Fügt dem Image Metadaten hinzu
- Пример:    
    `LABEL maintainer="yourname@example.com"`

#### RUN

- **Выполняет команду в контейнере на этапе сборки**
- Führt einen Befehl im Container während des Build-Prozesses aus
- Пример:
    `RUN apt-get update && apt-get install -y nginx`

#### CMD

- **Задает команду для выполнения при запуске контейнера**
- Legt den Befehl fest, der beim Starten des Containers ausgeführt wird
- Пример:
    `CMD ["nginx", "-g", "daemon off;"]`


#### EXPOSE

- **Документирует намерение контейнера слушать указанные порты**
- Dokumentiert die Absicht des Containers, auf den angegebenen Ports zu lauschen
- Пример:
    `EXPOSE 80`
#### ENV

- **Устанавливает переменные окружения**
- Setzt Umgebungsvariablen
- Пример:
    `ENV ENVIRONMENT=production`

#### ADD

- **Копирует файлы и каталоги в контейнер**
- Kopiert Dateien und Verzeichnisse in den Container
- Пример:
    `ADD localfile /path/in/container`

#### COPY

- **Копирует файлы и каталоги в контейнер**
- Kopiert Dateien und Verzeichnisse in den Container
- Пример:
    `COPY localfile /path/in/container`

#### ENTRYPOINT

- **Задает команду, которая будет выполняться при запуске контейнера**
- Legt den Befehl fest, der beim Starten des Containers ausgeführt wird
- Пример:
    `ENTRYPOINT ["nginx", "-g", "daemon off;"]`

#### VOLUME

- **Создает точку монтирования для внешних томов**
- Erstellt einen Mount-Punkt für externe Volumes
- Пример:
    `VOLUME ["/data"]`

#### USER

- **Задает пользователя, от имени которого будут выполняться команды**
- Legt den Benutzer fest, unter dem die Befehle ausgeführt werden
- Пример:
    `USER username`

#### WORKDIR

- **Устанавливает рабочий каталог для последующих команд**
- Setzt das Arbeitsverzeichnis für nachfolgende Befehle
- Пример:

    `WORKDIR /path/to/workdir`

#### ARG

- **Определяет переменные для передачи на этапе сборки**
- Definiert Variablen, die während des Build-Prozesses übergeben werden
- Пример:
    `ARG build_var=value`

#### ONBUILD

- **Задает инструкцию для выполнения в дочерних образах**
- Legt eine Anweisung fest, die in Child-Images ausgeführt wird
- Пример:

    `ONBUILD RUN echo "This runs on child image build"`



# Различия между CMD и ENTRYPOINT в Docker

### CMD

Перевод: Определяет команду по умолчанию для выполнения в контейнере.
- Definiert den Standardbefehl, der im Container ausgeführt werden soll.

- **Назначение**: Устанавливает команду по умолчанию, которую можно переопределить при запуске контейнера.
  - **Zweck**: Setzt einen Standardbefehl, der beim Starten des Containers überschrieben werden kann.
- **Переопределение**: Может быть заменена при использовании параметров командной строки `docker run`.
  - **Überschreibung**: Kann durch die Verwendung von Befehlszeilenargumenten mit `docker run` überschrieben werden.
- **Синтаксис в Dockerfile**: `CMD ["executable", "param1", "param2"]`
  - **Syntax in Dockerfile**: `CMD ["executable", "param1", "param2"]`

### ENTRYPOINT

Перевод: Определяет команду, которая всегда будет выполняться при запуске контейнера.
- Definiert den Befehl, der immer beim Starten des Containers ausgeführt wird.

- **Назначение**: Устанавливает команду, которую нельзя переопределить при запуске контейнера.
  - **Zweck**: Setzt einen Befehl, der beim Starten des Containers nicht überschrieben werden kann.
- **Переопределение**: Аргументы командной строки добавляются к ENTRYPOINT.
  - **Überschreibung**: Befehlszeilenargumente werden zu ENTRYPOINT hinzugefügt.
- **Синтаксис в Dockerfile**: `ENTRYPOINT ["executable", "param1", "param2"]`
  - **Syntax in Dockerfile**: `ENTRYPOINT ["executable", "param1", "param2"]`

### Комбинирование CMD и ENTRYPOINT

Перевод: Можно использовать вместе для задания команд и параметров по умолчанию.
- Können zusammen verwendet werden, um Standardbefehle und -parameter festzulegen.

- **Пример**:
  - **Beispiel**:

  ```Dockerfile
  ENTRYPOINT ["executable"]
  CMD ["param1", "param2"]
