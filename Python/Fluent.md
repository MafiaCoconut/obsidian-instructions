##### Начало работы 
Создать  папку `locales`

В папке `locales` создать подпапки с кодами языков, которые будут в проекте. 

В каждой подпапке создать файл с расширением `.ftl` куда будут записываться все переводы

Пример:
`locales\en\base_en.ftl`
`locales\ru\base_ru.ftl`

###### Инициализация
Создать файл `utils.fluent.py`

Внутрь прописать следующее 
```Python
from fluent.runtime import FluentLocalization, FluentResourceLoader

loader = FluentResourceLoader("locales/{locale}")
```

Создать переменные отвечающие  за вывод подходящего  перевода 
```Python
l10n_en = FluentLocalization(["en"], ["base_en.ftl"], loader)
l10n_ru = FluentLocalization(["ru"], ["base_ru.ftl"], loader)
```
Также можно добавить  следующее
```Python
list_of_available_languages = ['en', 'ru']

list_of_l10n = {
    'ru': l10n_ru,
    'en': l10n_en
}
```
Импортировав `list_of_available_languages` в нужную вам часть кода, можно получить список доступных языков для перевода

Импортировав `list_of_l10n` можно обратиться к нужному l10n по языковому коду 

##### Формат записи данных в .ftl
Если нужно, чтобы текст был многострочным, то 
```python
# base_ru.ftl
menu-main =  
<b>Главное меню</b>  
  
Выберите пункт меню.
```

Если текст однострочный, то
```python
# base_ru.ftl
reactivating-bot = Вы уже активировали бота!
```

Соответсвенно нужно создать переменные с **такими же названиями** в файлах `.ftl`  других языков.
##### Принцип работы
В файле, в котором нужно  добавить  мультиязычность импортируем list_of_l10n. 
Тут можно либо создать локально новую переменную под l10n или использовать  уже созданную переменную через list_of_l10n.
```Python
from utils.fluent import list_of_l10n
# Первый способ
language = 'en'
l10n = list_of_l10n[language]
text = l10n.format_value('reactivating-bot')
print(text) # You have already activated the bot!

# Второй способ
language = 'ru'
text = list_of_l10n[language].format_value('reactivating-bot')
print(text) # Вы уже активировали бота!
```

##### Создание динамических кнопок в клавиатурах aiogram
Требуемую клавиатуру нужно обернуть в функцию, которая будет создавать клавиатуру с учётом выбранного языка.
```python
def get_go_to_menu_main(l10n):  
	go_to_menu_main = InlineKeyboardMarkup(  
		inline_keyboard=[  
			[InlineKeyboardButton(text=l10n.format_value('to-menu-main'), callback_data="menu_main")]  
		]  
	)  
	
return go_to_menu_main
```

В этом примере мы передаём в функцию создания клавиатуры l10n, которую мы уже инициализировали до этого в основной функции.