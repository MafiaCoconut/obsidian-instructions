### Установка драйвера
Для работы Selenium понадобится скачать последнюю версию драйвера браузера

##### Firefox
Скачать [geckodriver][https://github.com/mozilla/geckodriver/releases]

**Важно!!**
Файл geckodriver.exe нужно поместить в одну папку с проектом

### Работа с кодом

 Добавление через import
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

from selenium.webdriver.firefox.options import Options as FirefoxOptions  
from selenium.webdriver.firefox.service import Service
```

###### Подключение драйвера на Windows
```python
self.driver = webdriver.Firefox()
```

###### Подключение драйвера на Raspberry Pi 
```python
FF_OPTIONS = [  
'--headless',  
'--no-sandbox',  
'--disable-xss-auditor',  
'--disable-web-security',  
'--ignore-certificate-errors',  
'--log-level=3',  
'--disable-notifications'  
]  
  
SET_PREF = {  
'general.useragent.override': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36',  
'permissions.default.desktop-notification': 1,  
'dom.webnotifications.enabled': 1,  
'dom.push.enabled': 1,  
'intl.accept_languages': 'en-US'  
}  
  
options = FirefoxOptions()  
[options.add_argument(opt) for opt in FF_OPTIONS]  
[options.set_preference(key, value) for key, value in SET_PREF.items()]  
  
path_to_geko = "/home/pi/Downloads/geckodriver"  
self.driver = webdriver.Firefox(service=Service(path_to_geko), options=options)
```

Важно!!
В переменной изменить путь до файла geckodriver


###### Открытия браузера через ссылку
```python
driver.get(url_link)
```

###### Чтобы получить элемент, нужно:
1. Открыть страницу
2. Навестить на нужный элемент
3. Открыть код элемента
4. Найти нужную часть кода
5. Нажать на него>Копировать>Копировать XPATH

###### Пример поиска элементов
```python
# Найти один элемент, подходящий под условие
item = driver.find_element(By.XPATH, f'//*[@id="button-plus"]')
# Найти все элементы, подходящие под условие
item = driver.find_elements(By.XPATH, f'//*[@id="button-plus"]')
```


Закрыть браузер
```python
driver.close()
```