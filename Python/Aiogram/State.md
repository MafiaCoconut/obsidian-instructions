###### Добавление через import
```python
from aiogram.fsm.state import StatesGroup, State
```

###### Создание класса State, для дальнейшего использования
```python
class SendFeedback(StatesGroup):  
	text = State()  
	check = State()
```

###### Imort класса для вызова нужной функции
```python
from aiogram.fsm.context import FSMContext
```

###### Создание функции, которую нужно вызвать через State
```python
@router.message(SendFeedback.text)  
async def send_feedback_form_text(message: Message, state: FSMContext):
	...

@router.message(SendFeedback.check)  
async def send_feedback_form_check(message: Message, state: FSMContext):
	...
```
Важно в router добавить класс State и параметр, через который нужно вызвать эту функцию

##### Методы  State
###### Изменение параметра, через который вызывать функцию
```python
await state.set_state(SendFeedback.check)
```

###### Запись в State данных
```python 
await state.update_data(text=message.text)
```
Перед тем как обновлять данные, сначала нужно их `state.set_state()`
###### Получение данных из State
```python
data = await state.get_data()

# Результат: {'text': 'сообщение', '..': '..'}
```

###### Очистка state
```python
await state.clear()
```

##### Пример работы State

Файл конфигурации state 'utils.states.py'
```python
from aiogram.fsm.state import StatesGroup, State


class SendFeedback(StatesGroup):  
	text = State()  
	check = State()
```

Файл из которого начинается State
```python
from aiogram.fsm.context import FSMContext


@router.message(Command("start"))  
async def start_handler(message: Message, state: FSMContext) -> None:  

	await state.set_state(SendFeedback.text)
```

Основной файл вызова функций
```python
from utils.states import SendFeedback


@router.message(SendFeedback.text)  
async def send_feedback_form_text(message: Message, state: FSMContext):
	await state.update_data(text=message.text)
	await state.set_state(SendFeedback.check)
	

@router.message(SendFeedback.check)
async def send_feedback_form_check(message: Message, state: FSMContext):
	await state.update_data(check=message.text)
	data = await state.get_data()
	print(data)
	await state.clear() 
```

##### Описание работы State: 
- В файлу utils.states инициализируется класс State по которому будет переключаться бот между вызовами функций.
- В основном файле начала вызова State после ввода в бота команды `/start` начинается активировать State.
-  В файле обработчиков  State сначала вызывается функция с обработчиком  SendFeedback.text . В ней активируется State следующей функции.