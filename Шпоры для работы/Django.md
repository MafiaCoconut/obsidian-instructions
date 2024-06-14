### Основные особенности Django

#### **ORM (Object-Relational Mapping)**:

- <font color="#00b050">Позволяет</font> взаимодействовать с базами данных через объекты Python.
- <font color="#00b050">Erlaubt</font> die Interaktion mit Datenbanken durch Python-Objekte.

#### **Административный интерфейс**:

-  <font color="#00b050">Встроенный </font> админ-интерфейс для  <font color="#00b050">управления </font> контентом.
-  <font color="#00b050">Eingebautes </font> Admin-Interface zur  <font color="#00b050">Verwaltung </font> von Inhalten.

#### **Аутентификация и авторизация**:

- Встроенные системы аутентификации пользователей и управления правами доступа.
- Eingebaute Systeme zur Benutzer-Authentifizierung und Zugriffssteuerung.

#### **URL Routing**:

- Гибкая система маршрутизации URL для  <font color="#00b050">определения </font> путей.
- Flexibles URL-Routing-System zur  <font color="#00b050">Definition </font> von Pfaden.

#### **Шаблоны (Templates)**:

- Движок шаблонов для генерации HTML страниц.
- Template-Engine zur Generierung von HTML-Seiten.

#### **Формы**:

- Упрощенное создание и валидация HTML-форм.
- Vereinfachte Erstellung und Validierung von HTML-Formularen.

### Основные файлы и директории Django

#### **manage.py**:

- Основной скрипт для управления проектом.
- Hauptskript zur Verwaltung des Projekts.

#### **settings.py**:

- Файл конфигурации проекта.
- Konfigurationsdatei des Projekts.

#### - **urls.py**:

-  <font color="#00b050">Определяет </font> маршруты URL для проекта.
-  <font color="#00b050">Definiert </font> die URL-Routen für das Projekt.

#### - **views.py**:

- Содержит <font color="#00b050">представления</font>, обрабатывающие <font color="#00b050">запросы</font> и возвращающие ответы.
- Enthält die <font color="#00b050">Ansichten</font>, die <font color="#00b050">Anfragen</font> verarbeiten und Antworten zurückgeben.

#### - **models.py**:

- Определяет модели данных.
- Definiert die Datenmodelle.


### Что такое миграции?

- Механизм для управления изменениями в структуре базы данных.
- Ein Mechanismus zur Verwaltung von Änderungen in der Datenbankstruktur.

### Основные функции миграций

#### **Создание таблиц**:
- Автоматическое создание таблиц в базе данных.
- Automatisches Erstellen von Tabellen in der Datenbank.

#### **Изменение таблиц**:

- Добавление, изменение или удаление столбцов и других структур.
- Hinzufügen, Ändern oder Entfernen von Spalten und anderen Strukturen.

#### **Синхронизация с моделями**:

- Поддержание базы данных в синхронизации с моделями Django.
- Halten der Datenbank in Synchronisation mit den Django-Modellen.

### Основные команды миграций

#### **makemigrations**:
- <font color="#00b050">Создает</font> новые миграции на основе изменений в моделях.
- <font color="#00b050">Erstellt</font> neue Migrationen basierend auf Änderungen in den Modellen.
	`python manage.py makemigrations`

#### **migrate**:
- <font color="#00b050">Применяет</font> и <font color="#00b050">откатывает</font> миграции к базе данных.
- <font color="#00b050">Wendet</font> Migrationen auf die Datenbank an und macht sie <font color="#00b050">rückgängig</font>.
	`python manage.py migrate`

#### **showmigrations**:
- Показывает список миграций и их статус.
- Zeigt eine Liste der Migrationen und ihren Status an.
	`python manage.py showmigrations`

#### **sqlmigrate**:
- Показывает SQL-запросы для указанной миграции.
- Zeigt die SQL-Abfragen für die angegebene Migration an.
	`python manage.py sqlmigrate appname migration_number`

### Создание миграций

#### **Автоматическое создание**:

- Создание миграций на основе изменений в models.py.
- Erstellung von Migrationen basierend auf Änderungen in models.py.

#### **Ручное создание**:

- Внесение изменений вручную для сложных случаев.
- Manuelles Erstellen von Änderungen für komplexe Fälle.

### Применение миграций

#### **Применение новых миграций**:
- Применение всех новых миграций к базе данных.
- Anwenden aller neuen Migrationen auf die Datenbank.
	`python manage.py migrate`

#### **Откат миграций**:
- <font color="#00b050">Откат</font> к предыдущей версии базы данных.
- <font color="#00b050">Rückgängigmachen</font> von Migrationen auf eine frühere Version der Datenbank.
	`python manage.py migrate appname migration_number`

### Понятие фикстур (fixtures)

#### **Fixtures**:
- Механизм для загрузки предварительных данных в базу данных.
- Ein Mechanismus zum Laden von Seed-Daten in die Datenbank.
	`python manage.py loaddata data.json`

### Пример миграции

- Пример создания и <font color="#00b050">применения</font> миграции.
- Ein Beispiel zum Erstellen und <font color="#00b050">Anwenden</font> einer Migration.

#### 1. Изменение модели (models.py):

```
class MyModel(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()

```

#### 2. Создание миграции:
`python manage.py makemigrations`

#### 3. Применение миграции:

`python manage.py migrate`

### Важные моменты

#### **Контроль версий**:

- Миграции должны быть включены в <font color="#00b050">систему контроля версий</font>.
- Migrationen sollten in die <font color="#00b050">Versionskontrollsysteme</font> aufgenommen werden.

#### **Совместимость с данными**:

- Убедитесь, что изменения не нарушат существующие данные.
- Stellen Sie sicher, dass Änderungen bestehende Daten nicht beschädigen.

#### **Тестирование миграций**:

- Всегда тестируйте миграции перед применением на продакшн.
- Testen Sie Migrationen immer vor dem Anwenden in der Produktion.