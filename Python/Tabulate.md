###### Добавление через import
```python
from tabulate import tabulate
```

###### Создание таблицы
```python
headers = ['name', 'description']
rows = [['cow', 'moo'], ['cat', 'meow']]

table = tabulate(rows, headers, tablefmt="pipe")
```

Вывод
```
| name   | description   |
|:-------|:--------------|
| cow    | moo           |
| cat    | meow          |
```

