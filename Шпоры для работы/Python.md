
## Datentyp

- unveränderbare im Sinne des belegten Speicherplatzes z.B. Zahlen (`int`, `float`, `complex`) sowie `tuple`, `string`
- veränderbare im Sinne des belegten Speicherplatzes z.B. `list`, `dict`, `set`

| Тип   | Название         |
| ----- | ---------------- |
| int   | Ganze Zahlen     |
| bool  | Wahrheitswerte   |
| float | Gleitkommazahlen |

---
###### Sequenzen

| Тип   | Название      |
| ----- | ------------- |
| str   | Zeichenketten |
| tuple | Tupel         |
| list  | Liste         |

---
###### Mappings

| Тип  | Название   |
| ---- | ---------- |
| dict | Dictionary |

---
##### Mengen

| Тип | Название |
| --- | -------- |
| set | Set      |
#### Unterschied == und is
== сравнивает значения/vergleicht Werte

is сравнивает адреса в памяти/vergleicht Adressen im Speicher


## Funktionen
###### args 
 - неограниченное количество дополнительных переменных в формате "значение" 
- unbegrenzte Anzahl zusätzlicher Variablen im Format <font color="#00b050">"Wert"</font>

###### kwargs
 - неограниченное количество дополнительных переменных в формате "ключ=значение" 
- unbegrenzte Anzahl zusätzlicher Variablen <font color="#00b050">im Format "Schlüssel=Wert"</font>


##### Annotationen (Аннотации)
<font color="#00b050">Пояснение</font> какое значение должны иметь переменная
<font color="#00b050">Erläuterung</font>, welchen Wert eine Variable haben sollte.

## Lambda
- Анонимная функция / Anonyme Funktion
- принимает любое количество аргументов / akzeptiert eine beliebige Anzahl von Argumenten
- В функции содержится неявный return / Die Funktion enthält eine implizite return
##### Примеры:
###### 1. Lambda функция для сложения двух чисел

```python
add = lambda x, y: x + y
print(add(2, 3))  # Вывод: 5
```
###### 2. Lambda функция для нахождения максимума из двух чисел

```python
maximum = lambda a, b: a if a > b else b
print(maximum(5, 10))  # Вывод: 10

```

###### 3. Lambda функция для фильтрации четных чисел из списка

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

even_numbers = list(filter(lambda x: x % 2 == 0, numbers)) print(even_numbers)  # Вывод: [2, 4, 6, 8, 10]
```

###### 4. Lambda функция для преобразования списка строк в их длины

```python
words = ["hello", "world", "python", "lambda"] 

lengths = list(map(lambda word: len(word), words)) print(lengths)  # Вывод: [5, 5, 6, 6]
```

###### 5. Lambda функция для сортировки списка словарей по ключу 'age'

```python

people = [{'name': 'Alice', 'age': 25}, {'name': 'Bob', 'age': 30}, {'name': 'Charlie', 'age': 20}] 

sorted_people = sorted(people, key=lambda person: person['age']) print(sorted_people)   

# Вывод: [{'name': 'Charlie', 'age': 20}, {'name': 'Alice', 'age': 25}, {'name': 'Bob', 'age': 30}]
```


## Oberflächliches und tiefes Kopieren (Поверхностное и глубокое копирование)

#### Oberflächliches Kopieren
Копирует в <font color="#7030a0">новую переменную</font> <font color="#00b0f0">ссылку</font> на уже <font color="#00b050">созданные объект</font>.
При изменении данных в одной переменной, они изменятся и во второй

Kopiert einen <font color="#00b0f0">Verweis</font> auf bereits <font color="#00b050">erstellte Objekte</font> in eine <font color="#7030a0">neue Variable</font>
Wenn Sie die Daten in einer Variablen ändern, werden sie sich auch in der zweiten ändern

#### Tiefes Kopieren
Копирует в новую переменную <font color="#00b050">новый объект</font> с <font color="#00b0f0">теми же данными</font>
при изменении данных в одной переменной они НЕ изменяются во второй

Kopiert ein neues Objekt mit <font color="#00b0f0">denselben Daten</font> in eine <font color="#00b050">neue Variable</font>.
Wenn sich die Daten in einer Variablen ändern, werden sie in der zweiten Variablen NICHT geändert



## Ternärer Operator (Тернарный оператор)

```python
x = 16
result = True if x % 2 == 0 else False
```
## Virtuelle Umgebung(Виртуальное окружение)

Копия чистого python выделенная специально для конкретного проекта, чтобы не засорять основной python библиотеками конкретного проекта

Eine Kopie von reinem Python wurde speziell für ein bestimmtes Projekt erstellt, um zu vermeiden, dass das Hauptpython mit projektspezifischen Bibliotheken verstopft wird

	`python -m venv venv`


## Классы
###### Klassen
<font color="#00b050">Шаблон</font> или <font color="#00b050">чертеж</font> для создания объектов (экземпляров).
Eine <font color="#00b050">Vorlage</font> oder <font color="#00b050">Zeichnung</font> zum Erstellen von Objekten (Exemplaren).

Определяет атрибуты и методы, которые будут принадлежать объектам
Definiert die Attribute und Methoden, die zu den Objekten gehören.

###### Objekten
<font color="#00b050">Экземпляр</font> класса
Eine <font color="#00b050">Instanz</font> der Klasse.

Конкретная <font color="#00b050">реализация</font> класса с собственными данными.
Eine spezifische <font color="#00b050">Implementierung</font> einer Klasse mit nativen Daten.

### Vererbung (Наследование)
Позволяет создавать новый класс на основе существующего.
Erstellt eine neue Klasse basierend auf einer vorhandenen Klasse.

Новый класс (дочерний) <font color="#00b050">наследует</font> атрибуты и методы <font color="#00b050">родительского</font> класса
Die neue Klasse (untergeordnete Klasse) <font color="#00b050">erbt</font> die Attribute und Methoden der <font color="#00b050">übergeordneten</font> Klasse.

### Polymorphismus und Methodenüberschreibungen (Полиморфизм и переопределение методов)

#### Polymorphismus
Die Fähigkeit eines Objekts, viele Formen anzunehmen. 

Methoden mit demselben Namen können sich in verschiedenen Kontexten unterschiedlich verhalten. 

#### Methoden überschreiben
Дочерний класс может переопределять методы родительского класса
Eine untergeordnete Klasse kann die Methoden der übergeordneten Klasse überschreiben.

### super()
#### Initialisieren der übergeordneten Klasse (Инициализация родительского класса)
```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # Вызов конструктора родительского класса
        self.breed = breed
```

#### Methoden der übergeordneten Klasse erweitern (Расширение методов родительского класса)
```python
class Animal: 
	def speak(self): 
		print("Animal makes a sound") 
class Dog(Animal): 
	def speak(self): 
		super().speak() # Вызов метода родительского класса print("Dog barks")
```

#### Mehrfachvererbung(Множественное наследование)
```python
class Animal:
    def __init__(self, name):
        self.name = name

class Canine:
    def __init__(self, breed):
        self.breed = breed

class Dog(Animal, Canine):
    def __init__(self, name, breed):
        super().__init__(name)  # Вызов конструктора Animal
        Canine.__init__(self, breed)  # Вызов конструктора Canine
```

#### 

### @staticmethod
Методы, которые не получают ссылку на экземпляр или класс.
Methoden, die keinen Verweis auf eine Exemplar oder Klasse erhalten.

### @abstractmethod
Используется для обозначения метода как абстрактного
Wird verwendet, um eine Methode als abstrakt zu bezeichnen

Абстракции нужны, для того, чтобы можно было создать <font color="#00b050">шаблон реализации</font> и <font color="#00b0f0">вызывать</font> в коде не абстрактный класс находящийся на уровне с Use cases и Services чтобы не нарушать принципов SOLID 

Abstraktionen sind erforderlich, damit Sie ein <font color="#00b050">Implementierungsmuster</font> erstellen und im Code eine abstrakte Klasse <font color="#00b0f0">aufrufen</font> können, die sich auf Use cases und Services-Ebene befindet, um die SOLID-Prinzipien nicht zu verletzen
### zugriffsberechtigungen (уровни доступа к переменным классов)

В python нет модификаторов доступа
#### public val

Доступен отовсюду, без <font color="#00b050">ограничений</font>.
Verfügbar von überall, ohne <font color="#00b050">Einschränkungen</font>.

Нет специальных синтаксических конструкций для <font color="#00b050">обозначения</font>
Es gibt keine speziellen syntaktischen Konstrukte zur <font color="#00b050">Bezeichnung</font>.

Атрибуты и методы по умолчанию являются публичными
Attribute und Methoden sind standardmäßig öffentlich.

#### private \_\_val
<font color="#00b050">Доступен только внутри класса</font>, не доступен из подклассов и внешнего кода
Nur <font color="#00b050">innerhalb einer Klasse verfügbar</font>, nicht über Unterklassen und externen Code verfügbar.

Обозначается <font color="#00b050">двумя подчеркиваниями</font> `__` перед именем атрибута или метода
Wird durch <font color="#00b050">zwei Unterstriche</font> __ vor dem Namen eines Attributs oder einer Methode gekennzeichnet.

Имя атрибута или метода изменяется путем манглинга имен, чтобы избежать случайного доступа
Der Name eines Attributs oder einer Methode wird geändert, indem die Namen benannt werden, um unbeabsichtigten Zugriff zu vermeiden
#### protected \_val
Предполагается, что атрибуты и методы должны быть доступны только внутри класса и его подклассов

Обозначается одним подчеркиванием `_` перед именем атрибута или метода.
Es wird davon ausgegangen, dass Attribute und Methoden nur innerhalb einer Klasse und ihrer Unterklassen verfügbar sein sollten.

Конвенция, но не enforced (необязательное ограничение)
Wird durch einen einzelnen Unterstrich _ vor dem Namen des Attributs oder der Methode gekennzeichnet.

## Декоратор

В python всё объекты.
In Python sind alle Objekte vorhanden.

Функция принимает аргумент функцию и возвращает функцию
Die Funktion akzeptiert das Argument der Funktion und gibt die Funktion zurück

```python
def decorator(func):
	der wrapper(*args, **kwargs):
		result = func(*args, **kwargs)
		return result
	return wrapper

@decorator
def some():
	pass

```

Декоратор с передачей данных
Dekorateur mit Datenübertragung
```python
def outer(a: int = 1)
	def decorator(func):
		der wrapper(*args, **kwargs):
			result = func(*args, **kwargs)
			return result
		return wrapper
	return decorator

@outer(12345)
def some():
	pass
```

## objektorientierte Programmierung(ООП)

#### Encapsulation
Инкапсуляция заключается в сокрытии внутреннего состояния объекта и предоставлении доступа к нему только через публичные методы. Это помогает защитить данные от некорректного использования и изменения.

 Die Kapselung besteht darin, den internen Zustand eines Objekts zu verbergen und nur durch öffentliche Methoden darauf zuzugreifen. Dies schützt Ihre Daten vor Missbrauch und Änderungen.
#### Inheritance (Наследование)
Наследование позволяет создавать новый класс на основе существующего. Новый класс (дочерний) наследует атрибуты и методы родительского класса, что позволяет использовать повторно код и расширять функциональность

Durch Vererbung können Sie eine neue Klasse basierend auf einer vorhandenen Klasse erstellen. Die neue Klasse (untergeordnete Klasse) erbt die Attribute und Methoden der übergeordneten Klasse, sodass Sie den Code wiederverwenden und die Funktionalität erweitern können

#### Polymorphism
Полиморфизм позволяет объектам разных классов обрабатывать вызовы методов с одинаковым именем. Это упрощает код, позволяя использовать один и тот же интерфейс для разных объектов.

Polymorphismus ermöglicht es Objekten verschiedener Klassen, Methodenaufrufe mit demselben Namen zu verarbeiten. Dies vereinfacht den Code, indem Sie die gleiche Schnittstelle für verschiedene Objekte verwenden können.
#### Abstraction
Абстракция заключается в выделении общих характеристик объектов и представлении их через абстрактные классы и методы. Она скрывает сложные детали реализации и показывает только необходимые характеристики и поведения.

Die Abstraktion besteht darin, die allgemeinen Eigenschaften von Objekten hervorzuheben und sie durch abstrakte Klassen und Methoden darzustellen. Es verbirgt komplexe Implementierungsdetails und zeigt nur die notwendigen Eigenschaften und Verhaltensweisen an.


## Итераторы
dies sind Objekte, mit denen Sie Elemente in Sammlungen (Listen, Tupel, Mengen usw.) nacheinander durchlaufen können.

\_\_iter\_\_(): Gibt den Iterator selbst zurück.
\_\_next\_\_(): Gibt das nächste Element der Auflistung zurück. 

## Генераторы
dies sind einfache und praktische Iteratoren, die mit der Funktion und dem Schlüsselwort `yield` anstelle von `return` erstellt werden.

Speichersparend: Es ist nicht erforderlich, die gesamte Sequenz im Speicher zu speichern.
Faule Berechnungen: Elemente werden nach Bedarf erstellt.
