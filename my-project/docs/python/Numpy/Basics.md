
# Базовые понятия

Информация из [статьи](https://ru.hexlet.io/courses/python-numpy/lessons/indexing-slicing/theory_unit)

``` python
# Импорт библиотеки numpy с псевдонимом np
import numpy as np

# Создание списка языка Python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Конвертация созданного списка в массив Numpy
numpy_numbers = np.array(numbers)

# Тип созданного объекта numbers
print(type(numbers))
# => <class 'list'>

# Тип созданного объекта numpy_numbers
print(type(numpy_numbers))
# => <class 'numpy.ndarray'>
```

```python
# Получение элемента по индексу из списка
print(numbers[2])
# => 2

# Получение элемента по индексу из numpy.ndarray
print(numpy_numbers[2])
# => 2
```

Продолжение скоро будет...


``` html
<p>HTML Document</p>
```
