# CI/CD: Краткая информация

### Что такое CI/CD?
CI (Continuous Integration)
CD (Continuous Delivery/Continuous Deployment)
- практики автоматизации разработки, тестирования и развертывания программного обеспечения.
- Praktiken zur Automatisierung der Entwicklung, des Testens und der Bereitstellung von Software.

#### Непрерывная интеграция (Continuous Integration)

- <font color="#00b050">Регулярное объединение изменений</font> в основной кодовой базе с автоматическим тестированием.
- <font color="#00b050">Regelmäßiges Zusammenführen von Änderungen</font> in den Hauptcode mit automatisierten Tests.

#### Частые коммиты

- Разработчики часто коммитят изменения в общий репозиторий.
- Entwickler committen häufig Änderungen in ein gemeinsames Repository.

#### Автоматическое тестирование

- Автоматическое выполнение тестов при каждом изменении в кодовой базе.
- Automatisierte Tests werden bei jeder Änderung im Code ausgeführt.

### Основные принципы CD

#### Непрерывная доставка (Continuous Delivery)

- Автоматизация <font color="#00b050">сборки</font>, тестирования и <font color="#00b050">подготовки</font> к <font color="#00b0f0">развертыванию</font> программного обеспечения.
- Automatisierung von <font color="#00b050">Build</font>, Test und <font color="#00b050">Vorbereitung</font> der Software für die <font color="#00b0f0">Bereitstellung</font>.

#### Готовность к выпуску

- Кодовая база всегда готова к <font color="#00b050">выпуску</font> в любое время.
- Der Code ist jederzeit für die <font color="#00b050">Bereitstellung</font> bereit.

#### Автоматизация развертывания

- Полная или частичная автоматизация <font color="#00b050">процесса развертывания</font>.
- Vollständige oder teilweise Automatisierung des <font color="#00b050">Bereitstellungsprozesses</font>.

#### Непрерывное развертывание (Continuous Deployment)

- Автоматическое <font color="#00b050">развертывание</font> всех изменений, прошедших тестирование, в <font color="#0070c0">рабочую среду</font>.
- Automatische <font color="#00b050">Bereitstellung</font> aller getesteten Änderungen in die <font color="#0070c0">Produktionsumgebung</font>.

### Wichtige Komponenten (Важные компоненты) CI/CD

#### Система контроля версий (VCS)

- Управление изменениями исходного кода (например, Git).
- Verwaltung von Änderungen im Quellcode (z.B. Git).

#### Система сборки (Build System)

- Инструменты для <font color="#00b050">автоматической сборки</font> и тестирования (например, Jenkins, Travis CI).
- Tools zur <font color="#00b050">automatischen Erstellung</font> und Testen (z.B. Jenkins, Travis CI).

#### Автоматическое тестирование

- Юнит-тесты, интеграционные тесты и другие формы тестирования для обеспечения качества.
- Unit-Tests, Integrationstests und andere Testformen zur Qualitätssicherung.

#### Bereitstellungstools (Инструменты развертывания) (Deployment Tools)

- Инструменты для автоматизации развертывания (например, Kubernetes, Ansible).
- Tools zur Automatisierung der Bereitstellung (z.B. Kubernetes, Ansible).

### Преимущества CI/CD

#### Повышение качества

- Раннее <font color="#00b050">обнаружение</font> <font color="#00b050">ошибок</font> и улучшение качества кода.
- Frühe <font color="#00b050">Fehlererkennung</font> und Verbesserung der Codequalität.

#### Ускорение выпуска

- Более быстрый и частый <font color="#00b050">выпуск</font> новых версий.
- Schnellere und häufigere <font color="#00b050">Veröffentlichung</font> neuer Versionen.

#### Снижение рисков

- Меньшие и более <font color="#00b050">управляемые</font> изменения, что снижает <font color="#00b050">риски развертывания</font>.
- Kleinere und besser <font color="#00b050">handhabbare</font> Änderungen, die das <font color="#00b050">Bereitstellungsrisiko</font> verringern.

#### Автоматизация

- Снижение ручного труда и повышение эффективности через автоматизацию.
- Reduktion manueller Arbeit und Steigerung der Effizienz durch Automatisierung.

### Внедрение CI/CD

#### Настройка системы контроля версий

- Использование репозиториев для управления исходным кодом.
- Nutzung von Repositories zur Verwaltung des Quellcodes.

#### Настройка системы сборки

- Интеграция инструментов для автоматического выполнения сборок и тестов.
- Integration von Tools zur automatischen Ausführung von Builds und Tests.

#### Конфигурирование пайплайна

- Создание пайплайна для автоматизации всех этапов от коммита до развертывания.
- Erstellung einer Pipeline zur Automatisierung aller Schritte vom Commit bis zur Bereitstellung.

#### Мониторинг и уведомления

- Настройка мониторинга и уведомлений для оперативного обнаружения проблем.
- Einrichtung von Überwachung und Benachrichtigungen zur schnellen Erkennung von Problemen.
