### Начало работы 
Создать  папку `locales`

В папке `locales` создать подпапки с кодами языков, которые будут в проекте. 

В каждой подпапке создать файл с расширением `.ftl` куда будут записываться все переводы

###### Пример:
`locales\en\base_en.ftl`
`locales\ru\base_ru.ftl`

### Инициализация
Создать файл `translation_service.py`

Внутри файла создаём класс `TranslationService`
```python
class TranslationService:
	def __init__(self):
		...
```

При инициализации нужно создать объект `FluentResourceLoader`, который будет указывать на папку, где содержатся все файлы с переводами. В конце пути нужно указать `{locale}`, чтобы при дальнейшей инициализации локализаторов, локали подставлялись сами.
```python
class TranslationService:
	def __init__(self):
		self.loader = FluentResourceLoader("infrastructure/locales/{locale}")
```

Далее внутри `__init__` нужно создать словарь, где ключ это языковая локаль, а значение это объект `FluentLocalization`
```python
class TranslationService:
	def __init__(self):
		self.loader = FluentResourceLoader("infrastructure/locales/{locale}")
		self.l10n = {
			'en': FluentLocalization(["en"], ["base_en.ftl"], self.loader),  
			'ru': FluentLocalization(["ru"], ["base_ru.ftl"], self.loader),
		}
```

Теперь нам нужно создать функцию, которая на вход будет получать название переменной в файле `.ftl` и языковую локаль. Функция будет возвращать полученное сообщение. Если такой переменной в файле не будет, функция вернёт саму переменную
```python
async def translate(self, message_id: str, locale: str, **kwargs):  
    if locale in self.l10n:  
        translation = self.l10n[locale].format_value(message_id, kwargs)  
        if translation == message_id:  
            logging.error(f"Message ID '{message_id}' not found for locale '{locale}'.")  
        return translation  
    else:  
        logging.error(f"Locale '{locale}' not supported.")  
        return f"[{message_id}]"
```

### Формат записи данных в .ftl
Если нужно, чтобы текст был многострочным, то 
```
# base_ru.ftl
menu-main =  
<b>Главное меню</b>  
  
Выберите пункт меню.
```

Если текст однострочный, то
```
# base_ru.ftl
reactivating-bot = Вы уже активировали бота!
```

Если нужно передать переменные в текст
```
dishes-header =  
    Меню столовой <b>{$canteen_name}</b>  
    Время последнего обновления: {$day} - {$time_last_parser}
```
Для заполнения таких данных, в `format_value` нужно передавать значения в формате `ключ: значение`

Соответсвенно нужно создать переменные с **такими же названиями** в файлах `.ftl`  других языков.

### Создание динамических кнопок в клавиатурах aiogram
Позже дополню

Создаём класс `KeyboardBuilder`
При инициализации передаём ему `translation_service`
Все `keyboards` возвращаем только через `async def get_<keyboards name>(locale: str)`
В функции `def get_<keyboards name>` в нужном месте вызываем `await self.translation_service.translate(message_id=<>, locale=<>)`
Функцию вернёт клавиатуру с переведёнными кнопками на переданную локаль