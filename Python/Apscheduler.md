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
			function_name, # Название функции, которую нужно вызвать по времени
			'cron', 
			id: str, # Id функции, чтобы быстро находить работу среди других
			hour: int, # В какой час запустить работу
			minute: int, #  В какую минуту часа запустить работу
			args=[...], # Аргументы, которые нужно передать function_name
)
```


###### Удаление работы
```python
scheduler.remove_job(
					job_id: str) # указать id работы, которую нужно удалить
```

###### Получить все работы
```python
jobs = scheduler.get_jobs()
```

