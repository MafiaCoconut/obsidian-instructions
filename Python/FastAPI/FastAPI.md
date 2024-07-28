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
@app.post("/user/createUser")
async def create_user(user: User|dict):
	await users_service.create_user(user=user)
	return {'message': "User created successful"}

```

```python
@app.get("users/getUser/{user_id})
async def get_user(user_id: int):
	user = await users_service.get_user(user_id=user_id)
	return {'user': user}

```

### Использование Enum
```python
from enum import Enum

class ModelName(str, Enum):
	golub = "golub"
	joker = "joker"
	plush = "plush"

@app.get("/models/{model_name}")
async def get_model(model_name: ModelName):
	if model_name is ModelName.golub:
		pass

	if model_name.value == "joker":
		pass
```
