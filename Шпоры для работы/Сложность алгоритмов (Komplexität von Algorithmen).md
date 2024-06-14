## Сложность алгоритмов
##### O(1) -  Konstante Komplexität
Die <span style="background:#d3f8b6">Ausführungszeit</span> ist <span style="background:#d3f8b6">unabhängig</span> von <span style="background:#d3f8b6">der Größe der Eingaben</span>.
Beispiel: Zugriff auf ein Array-Element über einen Index.
```python
def get_first_element(arr):
    return arr[0]
```

##### O(log n) - Logarithmische Komplexität

Die Ausführungszeit <span style="background:#d3f8b6">wächst</span> <span style="background:#d3f8b6">logarithmisch</span> mit <span style="background:#d3f8b6">zunehmender Eingabegröße</span>
Beispiel: Binäre Suche
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

```

##### O(n) - Lineare Komplexität

Die Ausführungszeit wächst linear mit zunehmender Eingabegröße
Beispiel: Durchlaufen eines Arrays
```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

```

##### O(n log n) - Lineare und logarithmische Komplexität

Die Ausführungszeit wächst schneller als linear, aber langsamer als quadratisch. 
Beispiel: Effektive Sortieralgorithmen (schnelle Sortierung, Merge-Sortierung).
```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result

```

##### O(n^2) - Quadratische Komplexität

Die Ausführungszeit nimmt mit zunehmender Eingabegröße quadratisch zu. 
Beispiel: Einfache Sortieralgorithmen (Blasen sortieren, Einfügen sortieren).
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

```


##### O(2n)  - Exponentielle Komplexität

Die Ausführungszeit wird mit jedem Hinzufügen eines neuen Elements verdoppelt.
Beispiel: Die Lösung des Problems eines Verkäufers durch Überbrückung.

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

```

##### O(n!) - Faktorielle Komplexität:

Die Ausführungszeit nimmt mit zunehmender Eingabegröße exponentiell zu.
Beispiel: Durchlaufen aller Permutationen.

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

```

