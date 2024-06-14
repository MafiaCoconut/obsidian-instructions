# Docker: Краткая информация

### Что такое Docker?

- Платформа для разработки, доставки и запуска приложений в контейнерах.
- Eine Plattform zur Entwicklung, Lieferung und Ausführung von Anwendungen in Containern.

### Docker Daemon

-  Фоновый <span style="background:#d3f8b6">процесс</span>, <span style="background:#d3f8b6">управляющий</span> контейнерами Docker.
- Ein <span style="background:#d3f8b6">Hintergrundprozess</span>, der Docker-Container <span style="background:#d3f8b6">verwaltet</span>.

### Docker Registry

- <span style="background:#d3f8b6">Хранилище</span> для Docker-образов (например, Docker Hub).
- Ein <span style="background:#d3f8b6">Speicherort</span> für Docker-Images (z.B. Docker Hub).

### .dockerignore

- Файл, <span style="background:#d3f8b6">указывающий</span>, какие файлы и <span style="background:#d3f8b6">директории</span> игнорировать при <span style="background:#b1ffff">сборке</span> образа.
- Eine Datei, die <span style="background:#d3f8b6">angibt</span>, welche Dateien und <span style="background:#d3f8b6">Verzeichnisse</span> beim <span style="background:#b1ffff">Erstellen</span> eines Images ignoriert werden sollen.

### Кэширование

- <span style="background:#d3f8b6">Используется</span> для ускорения <span style="background:#d3f8b6">сборки</span> Docker-образов, повторно используя <span style="background:#d3f8b6">слои</span>.
- Wird <span style="background:#d3f8b6">verwendet</span>, um den <span style="background:#d3f8b6">Aufbau</span> von Docker-Images zu beschleunigen, indem <span style="background:#d3f8b6">Schichten</span> wiederverwendet werden.

#  Image

#### Что такое Docker Image?

- Снимок файловой системы и настроек, необходимых для запуска контейнера.
- Ein Abbild des Dateisystems und der Einstellungen, die zum Ausführen eines Containers erforderlich sind.

#### Слои (Layers)

- Каждый образ состоит из нескольких слоев, созданных из <span style="background:#d3f8b6">команд</span> Dockerfile.
- Jedes Image besteht aus mehreren Schichten, die aus den <span style="background:#d3f8b6">Befehlen</span> einer Dockerfile erstellt werden.

# Docker Volumes

### Что такое Volume?

- Способ хранения данных вне контейнера.
- Eine Methode zur Speicherung von Daten außerhalb des Containers.

### Зачем нужны Volumes?

- Позволяют сохранять данные независимо от жизненного цикла контейнера.
- Erlauben die Speicherung von Daten unabhängig vom Lebenszyklus des Containers.

### Основные функции Volumes

#### **Персистентность данных**: 
- Данные сохраняются даже после удаления контейнера.
- Daten bleiben erhalten, selbst wenn der Container gelöscht wird.

#### **Совместное использование данных**: 
- Одни и те же данные могут использоваться несколькими контейнерами.
- Dieselben Daten können von mehreren Containern verwendet werden.

#### **Изоляция данных**: 
- <span style="background:#d3f8b6">Обеспечивают</span> изоляцию данных между хостом и контейнером.
- <span style="background:#d3f8b6">Gewährleisten</span> die Isolation von Daten zwischen Host und Container.
