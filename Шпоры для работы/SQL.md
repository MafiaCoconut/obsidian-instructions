# Команды

## DDL (Data Definition Language) / Язык определения данных

#### 1. **CREATE**:
   - Создает новую таблицу, базу данных, индекс или представление.
   - Пример:
     ```sql
     CREATE TABLE users (
         id INT PRIMARY KEY,
         name VARCHAR(100),
         email VARCHAR(100)
     );
     ```

#### 2. **ALTER**:
   - Изменяет структуру существующей таблицы.
   - Пример:
     ```sql
     ALTER TABLE users ADD COLUMN age INT;
     ```

#### 3. **DROP**:
   - Удаляет существующую таблицу, базу данных, индекс или представление.
   - Пример:
     ```sql
     DROP TABLE users;
     ```

#### 4. **TRUNCATE**:
   - Удаляет все строки из таблицы, но сохраняет структуру таблицы.
   - Пример:
     ```sql
     TRUNCATE TABLE users;
     ```

#### 5. **RENAME**:
   - Переименовывает таблицу.
   - Пример:
     ```sql
     ALTER TABLE users RENAME TO customers;
     ```

## DML (Data Manipulation Language) / Язык манипулирования данными

#### 1. **SELECT**:
   - Извлекает данные из одной или нескольких таблиц.
   - Пример:
     ```sql
     SELECT * FROM users;
     SELECT name, email FROM users WHERE age > 18;
     ```

#### 2. **INSERT**: (einsetzen)
   - Вставляет новые строки в таблицу.
   - Пример:
     ```sql
     INSERT INTO users (id, name, email) VALUES (1, 'Alice', 'alice@example.com');
     ```

#### 3. **UPDATE**: (erneuern)
   - Обновляет существующие строки в таблице.
   - Пример:
     ```sql
     UPDATE users SET email = 'newemail@example.com' WHERE id = 1;
     ```

#### 4. **DELETE**:
   - Удаляет существующие строки из таблицы.
   - Пример:
     ```sql
     DELETE FROM users WHERE id = 1;
     ```
#### 5. INNER JOIN:
- Возвращает только строки с соответствием в обеих таблицах.
- Gibt nur übereinstimmende Zeilen in beiden Tabellen zurück.
#### 6. LEFT JOIN:
- Возвращает все строки из левой таблицы и соответствующие строки из правой таблицы.
- Gibt alle Zeilen aus der linken Tabelle und die entsprechenden Zeilen aus der rechten Tabelle zurück.

- Пример: Все пользователи, включая Charlie, у которого нет заказов (NULL в `product`).
- Beispiel: Alle Benutzer, einschließlich Charlie, der keine Bestellungen hat (NULL im product).
## DCL (Data Control Language) / Язык управления данными

#### 1. **GRANT**:
   - Предоставляет пользователям или ролям привилегии на выполнение определенных операций.
   - Пример:
     ```sql
     GRANT SELECT, INSERT ON users TO someuser;
     ```

#### 2. **REVOKE**:
   - Отзывает привилегии у пользователей или ролей.
   - Пример:
     ```sql
     REVOKE SELECT, INSERT ON users FROM someuser;
     ```

## TCL (Transaction Control Language) / Язык управления транзакциями

#### 1. **COMMIT**:
   - Фиксирует все изменения, сделанные в текущей транзакции.
   - Пример:
     ```sql
     COMMIT;
     ```

#### 2. **ROLLBACK**:
   - Отменяет все изменения, сделанные в текущей транзакции.
   - Пример:
     ```sql
     ROLLBACK;
     ```

#### 3. **SAVEPOINT**:
   - Создает точку сохранения внутри транзакции, к которой можно вернуться.
   - Пример:
     ```sql
     SAVEPOINT sp1;
     ```

#### 4. **RELEASE SAVEPOINT**:
   - Удаляет установленную точку сохранения.
   - Пример:
     ```sql
     RELEASE SAVEPOINT sp1;
     ```

#### 5. **SET TRANSACTION**:
   - Определяет характеристики текущей транзакции.
   - Пример:
     ```sql
     SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
     ```

## Вспомогательные команды

#### 1. **DESCRIBE** или **DESC**:
   - Описывает структуру таблицы.
   - Пример:
     ```sql
     DESCRIBE users;
     ```

#### 2. **SHOW**:
   - Отображает список баз данных, таблиц, индексов и других объектов.
   - Пример:
     ```sql
     SHOW TABLES;
     SHOW DATABASES;
     ```

#### 3. **USE**:
   - Выбирает базу данных для текущего сеанса.
   - Пример:
     ```sql
     USE mydatabase;
     ```

## Команды для работы с индексами

#### 1. **CREATE INDEX**:
   - Создает индекс на одном или нескольких столбцах таблицы для ускорения операций поиска.
   - Пример:
     ```sql
     CREATE INDEX idx_name ON users (name);
     ```

#### 2. **DROP INDEX**:
   - Удаляет индекс из таблицы.
   - Пример:
     ```sql
     DROP INDEX idx_name ON users;
     ```

## Команды для работы с представлениями (Views)

#### 1. **CREATE VIEW**:
   - Создает виртуальную таблицу на основе результата запроса.
   - Пример:
     ```sql
     CREATE VIEW user_emails AS SELECT name, email FROM users;
     ```

#### 2. **DROP VIEW**:
   - Удаляет представление.
   - Пример:
     ```sql
     DROP VIEW user_emails;
     ```

## Команды для работы с триггерами (Triggers)

#### 1. **CREATE TRIGGER**:
   - Создает триггер, который выполняет определенное действие при выполнении указанного события (вставка, обновление, удаление).
   - Пример:
     ```sql
     CREATE TRIGGER before_insert_users
     BEFORE INSERT ON users
     FOR EACH ROW
     SET NEW.created_at = NOW();
     ```

#### 2. **DROP TRIGGER**:
   - Удаляет триггер.
   - Пример:
     ```sql
     DROP TRIGGER before_insert_users;
     ```


# Транзакции в SQL (Транзакции в SQL)

## Определение (Определение)

- **Транзакция** (Transaction) — это последовательность одной или нескольких операций с базой данных, которые выполняются как единое целое. Транзакция гарантирует, что все операции внутри нее будут выполнены успешно, или ни одна из них не будет выполнена (атомарность).
- **Eine Transaktion** (Transaction) ist eine Folge von einer oder mehreren Datenbankoperationen, die als eine Einheit ausgeführt werden. Eine Transaktion stellt sicher, dass alle Operationen innerhalb der Transaktion erfolgreich ausgeführt werden oder keine von ihnen ausgeführt wird (Atomarität).

## Основные характеристики транзакций (ACID) (Основные характеристики транзакций (ACID))

1. **Атомарность (Atomicity):**
   - Транзакция выполняется полностью или не выполняется вовсе. Если одна из операций в транзакции не удается, все изменения, сделанные другими операциями, отменяются.
   - Eine Transaktion wird entweder vollständig ausgeführt oder gar nicht. Wenn eine der Operationen in der Transaktion fehlschlägt, werden alle durchgeführten Änderungen zurückgesetzt.

2. **Согласованность (Consistency):**
   - Транзакция переводит базу данных из одного согласованного состояния в другое. Это означает, что все правила целостности базы данных должны быть соблюдены после завершения транзакции.
   - Eine Transaktion überführt die Datenbank von einem konsistenten Zustand in einen anderen. Dies bedeutet, dass alle Integritätsregeln der Datenbank nach Abschluss der Transaktion eingehalten werden müssen.

3. **Изоляция (Isolation):**
   - Результаты транзакции становятся видимыми другим транзакциям только после ее завершения. Это предотвращает взаимовлияние одновременно выполняющихся транзакций.
   - Die Ergebnisse einer Transaktion werden anderen Transaktionen erst nach deren Abschluss sichtbar. Dies verhindert die gegenseitige Beeinflussung gleichzeitig ausgeführter Transaktionen.

4. **Долговечность (Durability):**
   - После завершения транзакции (commit) ее результаты сохраняются в базе данных и не теряются, даже если система выйдет из строя.
   - Nach dem Abschluss einer Transaktion (Commit) werden ihre Ergebnisse in der Datenbank gespeichert und gehen nicht verloren, selbst wenn das System ausfällt.

## Основные команды для работы с транзакциями (Основные команды для работы с транзакциями)

1. **BEGIN TRANSACTION** или **START TRANSACTION:**
   - Начинает новую транзакцию.
   - Beginnt eine neue Transaktion.
   - Пример:
   - Beispiel:
     ```sql
     BEGIN TRANSACTION;
     ```

2. **COMMIT:**
   - Фиксирует все изменения, сделанные в текущей транзакции, и завершает транзакцию.
   - Bestätigt alle Änderungen, die in der aktuellen Transaktion vorgenommen wurden, und schließt die Transaktion ab.
   - Пример:
   - Beispiel:
     ```sql
     COMMIT;
     ```

3. **ROLLBACK:**
   - Отменяет все изменения, сделанные в текущей транзакции, и завершает транзакцию.
   - Macht alle Änderungen rückgängig, die in der aktuellen Transaktion vorgenommen wurden, und schließt die Transaktion ab.
   - Пример:
   - Beispiel:
     ```sql
     ROLLBACK;
     ```

4. **SAVEPOINT:**
   - Создает точку сохранения внутри транзакции, к которой можно вернуться с помощью команды ROLLBACK TO SAVEPOINT.
   - Erstellt einen Speicherpunkt innerhalb einer Transaktion, zu dem mit dem Befehl ROLLBACK TO SAVEPOINT zurückgekehrt werden kann.
   - Пример:
   - Beispiel:
     ```sql
     SAVEPOINT sp1;
     ```

5. **ROLLBACK TO SAVEPOINT:**
   - Отменяет изменения, сделанные после указанной точки сохранения.
   - Macht die Änderungen rückgängig, die nach dem angegebenen Speicherpunkt vorgenommen wurden.
   - Пример:
   - Beispiel:
     ```sql
     ROLLBACK TO SAVEPOINT sp1;
     ```

6. **RELEASE SAVEPOINT:**
   - Удаляет точку сохранения.
   - Löscht den Speicherpunkt.
   - Пример:
   - Beispiel:
     ```sql
     RELEASE SAVEPOINT sp1;
     ```

## Пример использования транзакций (Пример использования транзакций)

```sql
BEGIN TRANSACTION;

INSERT INTO accounts (account_id, balance) VALUES (1, 1000);
INSERT INTO accounts (account_id, balance) VALUES (2, 2000);

UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;

COMMIT;

```



# Уровни изоляции транзакций в SQL (Уровни изоляции транзакций в SQL)

## Определение (Определение)

Die Isolationsstufen bestimmen, wie stark Änderungen, die von einer Transaktion vorgenommen werden, für andere Transaktionen sichtbar sind. Sie beeinflussen, wie Transaktionen miteinander interagieren können und welche Probleme beim gleichzeitigen Zugriff auf Daten auftreten können. (Уровни изоляции определяют степень видимости изменений, внесенных одной транзакцией, для других транзакций. Они влияют на то, как транзакции могут взаимодействовать друг с другом и какие проблемы могут возникнуть при одновременном доступе к данным.)

## Основные уровни изоляции (Основные уровни изоляции)

1. **Read Uncommitted (Чтение неподтвержденных данных)**
   - **Описание:** Транзакции могут видеть изменения, внесенные другими транзакциями, даже если эти изменения еще не были зафиксированы (коммитированы).
   - **Проблемы:** Возможны "грязные чтения" (dirty reads), когда одна транзакция читает данные, которые могут быть откатаны другой транзакцией.
   - **Пример:** 
     ```sql
     SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
     ```

2. **Read Committed (Чтение подтвержденных данных)**
   - **Описание:** Транзакция видит только те изменения, которые были зафиксированы другими транзакциями. Неподтвержденные изменения недоступны для чтения.
   - **Проблемы:** Возможны "неповторяющиеся чтения" (non-repeatable reads), когда данные, прочитанные в одной транзакции, могут быть изменены другой транзакцией перед завершением первой транзакции.
   - **Пример:** 
     ```sql
     SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
     ```

3. **Repeatable Read (Повторяемое чтение)**
   - **Описание:** Гарантирует, что данные, прочитанные одной транзакцией, не могут быть изменены другой транзакцией до завершения первой транзакции. Однако возможны "фантомные чтения" (phantom reads), когда новые строки добавляются другой транзакцией и становятся видимыми.
   - **Проблемы:** Возможны "фантомные чтения" (phantom reads), когда новая строка, добавленная другой транзакцией, становится видимой для текущей транзакции при повторном чтении.
   - **Пример:** 
     ```sql
     SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
     ```

4. **Serializable (Сериализуемый)**
   - **Описание:** Обеспечивает наивысший уровень изоляции, гарантируя, что транзакции выполняются последовательно. Каждая транзакция выполняется так, как будто она является единственной, работающей с базой данных в данный момент.
   - **Проблемы:** Может привести к снижению производительности из-за блокировок и ожиданий.
   - **Пример:** 
     ```sql
     SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
     ```

## Проблемы изоляции (Проблемы изоляции)

1. **Грязное чтение (Dirty Read)**
   - Описание: Транзакция читает данные, которые были изменены другой транзакцией, но еще не зафиксированы.
   - Пример: Уровень изоляции Read Uncommitted.

2. **Неповторяющееся чтение (Non-repeatable Read)**
   - Описание: Данные, прочитанные в одной транзакции, могут быть изменены другой транзакцией до завершения первой транзакции.
   - Пример: Уровень изоляции Read Committed.

3. **Фантомное чтение (Phantom Read)**
   - Описание: Новые строки, добавленные другой транзакцией, могут стать видимыми для текущей транзакции при повторном чтении данных.
   - Пример: Уровень изоляции Repeatable Read.

## Заключение (Заключение)

Уровни изоляции транзакций играют важную роль в управлении взаимодействиями между одновременными транзакциями. Правильный выбор уровня изоляции помогает сбалансировать потребности в целостности данных и производительности системы. (Уровни изоляции транзакций играют важную роль в управлении взаимодействиями между одновременными транзакциями. Правильный выбор уровня изоляции помогает сбалансировать потребности в целостности данных и производительности системы.)
