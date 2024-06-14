### 1. Единообразие интерфейса (Uniform Interface)

Перевод: Определяет интерфейс взаимодействия между клиентом и сервером.

- Definiert die Schnittstelle für die Interaktion zwischen Client und Server.
    
- **Ресурсные идентификаторы**:
    
    - Перевод: Каждый ресурс имеет уникальный URL.
    - Jede Ressource hat eine eindeutige URL.
- **Манипуляции ресурсами через представления**:
    
    - Перевод: Операции над ресурсами выполняются с помощью их представлений (например, JSON, XML).
    - Operationen auf Ressourcen werden über ihre Darstellungen (z.B. JSON, XML) durchgeführt.
- **Самоописываемые сообщения**:
    
    - Перевод: Каждое сообщение содержит достаточно информации для обработки запроса.
    - Jede Nachricht enthält genügend Informationen zur Verarbeitung der Anfrage.
- **Гипермедиа в качестве движущей силы приложений (HATEOAS)**:
    
    - Перевод: Клиент использует гиперссылки для взаимодействия с ресурсами.
    - Der Client verwendet Hyperlinks zur Interaktion mit Ressourcen.

### 2. Клиент-сервер (Client-Server)

Перевод: Отделение пользовательского интерфейса от хранения данных для улучшения переносимости и масштабируемости.

- Trennung der Benutzeroberfläche von der Datenspeicherung zur Verbesserung der Portabilität und Skalierbarkeit.
    
- **Клиент**:
    
    - Перевод: Отвечает за пользовательский интерфейс и взаимодействие с пользователем.
    - Verantwortlich für die Benutzeroberfläche und die Interaktion mit dem Benutzer.
- **Сервер**:
    
    - Перевод: Управляет хранением данных и логикой обработки запросов.
    - Verantwortlich für die Datenverwaltung und die Abfrageverarbeitung.

### 3. Отсутствие состояния (Stateless)

Перевод: Каждый запрос от клиента к серверу должен содержать всю необходимую информацию для его обработки.

- Jede Anfrage vom Client zum Server muss alle notwendigen Informationen zur Verarbeitung enthalten.
    
- **Нет хранения сеансов**:
    
    - Перевод: Сервер не сохраняет информацию о предыдущих запросах клиента.
    - Der Server speichert keine Informationen über frühere Anfragen des Clients.

### 4. Кеширование (Cacheable)

Перевод: Ответы могут быть помечены как кэшируемые или некэшируемые для повышения производительности.

- Antworten können als cachefähig oder nicht cachefähig gekennzeichnet werden, um die Leistung zu verbessern.
    
- **Кэшируемые ответы**:
    
    - Перевод: Ответы могут храниться на клиенте или промежуточном сервере для повторного использования.
    - Antworten können auf dem Client oder einem zwischengeschalteten Server gespeichert werden.

### 5. Многоуровневая система (Layered System)

Перевод: Архитектура может быть разделена на иерархические слои для улучшения масштабируемости и управляемости.

- Die Architektur kann in hierarchische Ebenen unterteilt werden, um die Skalierbarkeit und Verwaltbarkeit zu verbessern.
    
- **Промежуточные серверы**:
    
    - Перевод: Прокси и шлюзы могут использоваться для улучшения масштабируемости.
    - Proxies und Gateways können zur Verbesserung der Skalierbarkeit verwendet werden.

### 6. Код по требованию (Code on Demand) (опционально)

Перевод: Сервер может передавать исполняемый код клиенту для выполнения (например, JavaScript).

- Der Server kann ausführbaren Code an den Client zur Ausführung senden (z.B. JavaScript).
    
- **Опциональность**:
    
    - Перевод: Этот принцип является необязательным и может не применяться во всех RESTful системах.
    - Dieses Prinzip ist optional und muss nicht in allen RESTful-Systemen angewendet werden.