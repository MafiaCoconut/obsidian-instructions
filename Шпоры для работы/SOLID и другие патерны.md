# SRP: Single Responsobility Principle
Prinzip der einzigen Verantwortung (Принцип единственной ответственности)

#### Hauptsache (Основная суть)
Ein Modul hat nur einen Grund für eine Änderung (модуль имеет одну и только одну причину для изменения)

##### WAS DAS TATSÄCHLICH BEDEUTET (ЧТО НА САМОМ ДЕЛЕ ИМЕЕТСЯ ВВИДУ)
Ein Modul sollte nur für einen einzigen Akteur verantwortlich sein. Akteur - eine Gruppe von Menschen (Модуль должен отвечать за одного и только за одного актора. актор-группа людей)

#### Erklärung (Объяснение)
Es gibt mehrere Personengruppen, die dieselbe Funktion für unterschiedliche Zwecke verwenden. Einem Akteur musste etwas im Code geändert werden, was den Code für den zweiten Akteur kaputt gemacht hat. Um dies zu vermeiden, muss die Funktionalität für jeden Akteur getrennt werden. (У нас есть несколько груп лиц, которые используют одну и ту же функцию для разных целей. Одному актору понадобилось, что-то изменить в коде, но это сломало код для второго актора. Чтобы это избежать, нужно разделять функционал для каждого актора)

##### Lösungsvarianten (Варианты решения)
- Erstellung separater Klassen für jeden Akteur (Создание отдельных классов под каждого актора)
- Verwendung des Fassade-Musters (eine Klasse, aber sie greift auf drei verschiedene kleinere Klassen zu) (Использовать шаблон фасад(1 класс, но он обращается к трём разным классам поменьше))

# OCP: Open - Closed Principle
Prinzip der Offenheit und Geschlossenheit (принцип открытости/закрытости)

#### Hauptsache (Основная суть)
Programmeinheiten (Klassen) sollten offen für Erweiterung, aber geschlossen für Änderungen sein (Программные сущности(классы) должны быть открыты для расширения и закрыты для изменения)

##### Erklärung (Объяснение)
Wenn wir eine Basisklasse haben, sollten wir sie nicht bei jeder Gelegenheit ändern, sondern für jede neue Situation eine neue Klasse erstellen, die von der Basisklasse erbt. (Если у нас есть базовый класс, то мы не должны при любом удобной случае его изменять, а наоборот под каждую новую ситуацию создавать новый класс, который будет наследоваться от базового класса)

# LSP: Liskov Substitution Principle
Liskovsches Substitutionsprinzip (принцип подстановки Барбары Лисков)

#### Hauptsache (Основная суть)
Wenn für jedes Objekt o1 vom Typ S ein Objekt o2 vom Typ T existiert, so dass für alle Programme P, die im Terminal T definiert sind, das Verhalten von P sich nicht ändert, wenn o1 anstelle von o2 eingesetzt wird, dann ist S ein Subtyp von T. (Если для каждого объекта о1 типа S существует такой объект о2 типа Т, что для всех программ Р, определённых в терминале T, поведение Р не изменяется при подстановке о1 вместо о2, то S является подтипом Т.)

##### Erklärung (Объяснение)
Wir haben eine Klasse *License*, die die Elternklasse für die Klassen *Personal Licence (PL)* und *Business Licence (BL)* ist. Und wenn wir beim Zugriff aus der Klasse Billing auf License sowohl PL als auch BL ohne Fehler verwenden können, dann wird das LSP eingehalten. (У нас есть класс *License*, который является родителем для классов *Personal Licence(PL)* и *Business Licence(BL)*. И если при обращении из класса Billing к Licence мы можем использовать без ошибок как PK, так и BL, то LSP соблюдается)

# ISP Interface Segregation Principle 
Prinzip der Schnittstellentrennung (Принцип разделения интерфейсов)

#### Hauptsache (Основная суть)
Abhängigkeiten von allem vermeiden, was nicht verwendet wird (Избегать зависимости от всего, что не используется)

##### Erklärung (Объяснение)
Wenn ein Teil der Schnittstelle den zweiten Teil nicht verwendet, aber von ihm abhängt, sollten diese Schnittstellen getrennt werden. (Если какая-то часть интерфейса не использует вторую часть, но зависит от неё, то нужно разделить эти интерфейсы)

# DIP Dependecy Inversion Principle
Prinzip der Abhängigkeitsinversion (Принцип инверсии зависимости)

#### Hauptsache (Основная суть)
Der Code, der die High-Level-Politik implementiert, sollte nicht vom Code abhängen, der Low-Level-Details implementiert. Im Gegenteil, die Details sollten von der Politik abhängen. (Код реализующий высокоуровневую политику, не должен зависеть от кода, реализующего низкоуровневые детали. Напротив, детали должны зависеть от политики)

#### Wichtige Regeln (Важные правила)
- Verweisen Sie nicht auf veränderliche konkrete Klassen. Verweisen Sie auf abstrakte Klassen. (Не ссылайтесь на изменчивые конкретные классы. Ссылаться нужно на абстрактные классы)
- Erben Sie nicht von veränderlichen konkreten Klassen. (Не наследуйте изменчивые конкретные классы)
- Überschreiben Sie keine konkreten Funktionen. Durch das Überschreiben von Funktionen beseitigen Sie die Abhängigkeit nicht, sondern erben tatsächlich. Um solche Abhängigkeiten zu verwalten, sollten Sie die Funktion abstrakt machen und mehrere Implementierungen davon erstellen. (Не переопределяйте конкретные функции. Переопределением функций, вы не устраняете зависимость, а фактически наследуем. Для управления подобными зависимостями нужно сделать функцию абстрактной и создать несколько её реализаций)
- Verweisen Sie niemals auf Namen konkreter und veränderlicher Entitäten. (Никогда не ссылайтесь на имена конкретных и изменчивых сущностей)


# Dry (Dont repeat yourself)
Es ist ein Prinzip, das betont, wie wichtig es ist, wiederverwendbaren Code zu schreiben, um Doppelarbeit zu vermeiden. Wenn Sie dem DRY-Prinzip folgen, stellen Sie sicher, dass jeder Code einem einzigen Zweck dient und an mehreren Stellen in Ihrer Anwendung verwendet werden kann, ohne dass er neu geschrieben werden muss.


# KISS(Keep  It Simple, Stupid)

KISS steht für Keep It Simple, Stupid. Es ist ein Prinzip, das betont, wie wichtig es ist, Ihren Code einfach und leicht verständlich zu halten. Wenn Sie dem KISS-Prinzip folgen, stellen Sie sicher, dass Ihr Code lesbar und wartbar ist, was Zeit sparen und die Wahrscheinlichkeit verringern kann, dass Fehler auftreten.

# Yagni (You Ain't Gonna Need It)



