###### Добавление через import
```python
from bs4 import BeautifulSoup

import requests
```

Получение кода страницы
```python
url = 'url_link'  
response = requests.get(url)  
self.soup = BeautifulSoup(response.content, 'html.parser')
```

Поиск подходящего элемента
```python
elements = self.soup.find_all('tr',  
{
	'data-canteen': canteen_number, 
	'data-date': date,  
})
```

tr -  тег элемента
data-canteen - один из пунктов элемента, по которому ищется элемент
data-date - один из пунктов элемента, по которому ищется элемент

Вывод текста элемента
```python
for element in elements:  
	dishes.append(element.text.strip())  
```

