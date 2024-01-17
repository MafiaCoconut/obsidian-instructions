###### Добавление через import
```python
from datetime import datetime
```


###### Получить время 
```python
dt = datetime.now()
"Команда вызова |Результат"
dt               2023-11-22 19:08:41.114854
dt.hour:         19
dt.minute:       8
dt.second:       41
dt.time():       19:08:41.114854
dt.day:          22
dt.month:        11
dt.year:         2023
dt.isoweekday(): 3
dt.date():       2023-11-22

```

###### Записать собственную переменную в тип datetime
```python
dt = '2023-11-22 19:08:41.114854'
date_time_obj = datetime.strptime(dt, '%Y-%m-%d %H:%M:%S.%f')
```
Формат можно менять, в зависимости от нужд



