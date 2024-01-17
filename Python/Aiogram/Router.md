##### Создание функций обработчиков сообщений
```python
from aiogram import Router

router = Router()
```

###### Функция вывода заглушки на необъявленное сообщение/команду
```python
@router.message()  
async def echo_handler(message: Message) -> None:  
	await message.answer("")
```
В `@router.message()` нужно указать условие, при котором вызывается именно эта функция.

##### Примеры:
###### Обработчик команды /start
```python
@router.message(CommandStart())  
async def command_start_handler(message: Message) -> None:
	...
```

###### Обработчик редактируемой команды
```python
@router.message(Command("main_menu"))  
async def main_menu_handler(message: Message) -> None:
	...
```

