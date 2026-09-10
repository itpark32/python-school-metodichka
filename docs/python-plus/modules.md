# Модули и несколько файлов

<p class="reading-time">Чтение: 7 минут · Практика: 18 минут</p>
<div class="tags"><span class="tag tag--plus">Python+</span></div>

Каждый `.py`-файл можно использовать как модуль. Разделяйте программу, когда функции образуют понятные группы.

!!! abstract "Фокус"
    - **Нужно знать:** `import module`, `from module import function`.
    - **Нужно уметь:** вызвать функцию из соседнего файла.

```text
project/
├── main.py
└── math_utils.py
```

```python
# math_utils.py
def is_even(number):
    return number % 2 == 0
```

```python
# main.py
from math_utils import is_even

number = int(input())
print(is_even(number))
```

При `import math_utils` вызов будет `math_utils.is_even(number)`, и происхождение функции видно сразу.

!!! info "Точка запуска"
    Код внутри `if __name__ == "__main__":` выполняется при прямом запуске файла, но не при импорте.

## Мини-практика

1. Вынесите функции делимости. 2. Импортируйте модуль целиком. 3. Добавьте функцию простоты.

## Проверьте себя

Что является модулем? Чем различаются две формы импорта? Зачем точка запуска?

## Где пригодится

- **Python+:** небольшие учебные программы без перехода к сложной архитектуре.
- **Следующая тема:** [исключения](exceptions.md).

<div class="topic-nav"><a href="../../graphs/paths/">← Графы</a><a href="../exceptions/">Исключения →</a></div>
