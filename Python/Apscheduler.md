###### Добавление через import
```python
from apscheduler.schedulers.asyncio import AsyncIOScheduler
```

###### Инициализация
```python
scheduler = AsyncIOScheduler()
```

###### Запуск 
```python
scheduler.start()
```

###### Добавление работы
```python
scheduler.add_job(
			func: Callable = function_name,
			trigger: str = 'cron', 
			id: str,
			hour: int,
			minute: int,
			args=[...], # Аргументы, которые нужно передать function_name
)
```
###### Параметры
```
:param int|str year: 4-digit year  
:param int|str month: month (1-12)  
:param int|str day: day of month (1-31)  
:param int|str week: ISO week (1-53)  
:param int|str day_of_week: number or name of weekday (0-6 or mon,tue,wed,thu,fri,sat,sun)  
:param int|str hour: hour (0-23)  
:param int|str minute: minute (0-59)  
:param int|str second: second (0-59)  
:param datetime|str start_date: earliest possible date/time to trigger on (inclusive)  
:param datetime|str end_date: latest possible date/time to trigger on (inclusive)  
:param datetime.tzinfo|str timezone: time zone to use for the date/time calculations (defaults  
    to scheduler timezone):param int|None jitter: delay the job execution by ``jitter`` seconds at most
```

###### Удаление работы
```python
scheduler.remove_job(job_id: str) # указать id работы, которую нужно удалить
```

###### Получить все работы
```python
jobs = scheduler.get_jobs()
```

