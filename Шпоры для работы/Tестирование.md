
Tests müssen immer geschrieben werden
## Виды тестов
###  **Komponententest (Unit Testing)**
    - Тестирование отдельных частей программы (функции, методы, классы).
    - Testen einzelner Teile des Programms (Funktionen, Methoden, Klassen)
    
###  **Integrationstest (Integration Testing)**
    - Тестирование взаимодействия между различными компонентами системы.
    - Testen der Interaktion zwischen verschiedenen Komponenten des Systems.
    
### **Funktionstest (Functional Testing)**
    - Проверка работы программы в соответствии с требованиями.
    - Überprüfen Sie den Betrieb des Programms entsprechend den Anforderungen.
    
###  **Akzeptanztest (Acceptance Testing)**
    - Проверка системы на соответствие бизнес-требованиям.
    - Überprüfen Sie das System, um die geschäftlichen Anforderungen zu erfüllen.
    
###  **Leistungstests (Performance Testing):**
    - Проверка скорости и эффективности программы.
    - Überprüfen Sie die Geschwindigkeit und Wirksamkeit des Programms


## Библиотеки
### unittest
```python
import unittest

class TestMath(unittest.TestCase):
    def test_addition(self):
        self.assertEqual(1 + 1, 2)

if __name__ == '__main__':
    unittest.main()
```


### pytest
```python
import pytest
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker
from canteens_service import Base, CanteensService, CanteensOrm

@pytest.fixture(scope='module')
def engine():
    return create_engine('sqlite:///:memory:')

@pytest.fixture(scope='module')
def tables(engine):
    Base.metadata.create_all(engine)
    yield
    Base.metadata.drop_all(engine)

@pytest.fixture(scope='function')
def session(engine, tables):
    connection = engine.connect()
    transaction = connection.begin()
    Session = sessionmaker(bind=connection)
    session = Session()
    yield session
    session.close()
    transaction.rollback()
    connection.close()

def test_add_and_get_canteen(session):
    service = CanteensService(session)
    canteen_id = service.add_canteen("Main Canteen")
    canteen = service.get_canteen(canteen_id)
    assert canteen is not None
    assert canteen.name == "Main Canteen"

```

- **Запуск конкретного тестового файла:**
    
    `pytest path/to/test_file.py`
    
- **Запуск конкретного тестового класса или метода:**
    
	`pytest path/to/test_file.py::TestClassName pytest` 
	`path/to/test_file.py::TestClassName::test_method_name`


## Mock
Es  ist eine Simulation eines realen Objekts, das in Tests verwendet wird.

Es kann das Verhalten eines realen Objekts nachahmen, die angegebenen Werte zurückgeben und die Interaktion mit ihm verfolgen (z. B. Methodenaufrufe).