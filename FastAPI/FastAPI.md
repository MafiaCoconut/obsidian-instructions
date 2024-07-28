### Инициализация
```python
from fastapi import FastAPI
app = FastAPI()
```

### Функция, которая запускается при запуске сервера
```python
async def lifespan(app: FastAPI):
	...

app = FastAPI(lifespan=lifespan)
```


### Создание endpoint
```python
@app.post("")
async def create_user(user: User):
	await users_service.create_user(user=user)
	return {'message': "User created sucksessful"}

```
