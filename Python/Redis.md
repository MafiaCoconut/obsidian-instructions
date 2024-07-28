## Установка


```bash
pip install redis
pip install redis[hiredis]
```

## Инициализация
```python
r = redis.Redis(
	host="127.0.0.1", 
	port=6379, 
	decode_responses=True
)
```

## Запись и получение простых данных
```python
r.hset('foo', 'bar')

foo - ключ
bar - значение
```

```python
r.hset('user-543256', mapping={
	'name': 'John',
	'surname': 'Wick',
	'age': 40
})

r.hgetall('user-543256')
#{'name': John, 'surname': Wick, 'age': 40}
```

