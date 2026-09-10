# Простые алгоритмы сортировки

<p class="reading-time">Чтение: 9 минут · Практика: 20 минут</p>
<div class="tags"><span class="tag">9–11 класс</span></div>

Сортировка переставляет элементы по порядку. Школьные алгоритмы нужны для понимания, хотя в обычном Python используют встроенную сортировку.

!!! abstract "Фокус"
    - **Нужно знать:** пузырёк, выбор и вставки.
    - **Нужно уметь:** объяснить одну итерацию каждого алгоритма.

```python
# Пузырьковая: большой элемент всплывает вправо
for end in range(len(numbers) - 1, 0, -1):
    for i in range(end):
        if numbers[i] > numbers[i + 1]:
            numbers[i], numbers[i + 1] = numbers[i + 1], numbers[i]
```

```python
# Выбором: ставим минимум на очередное место
for left in range(len(numbers)):
    minimum = left
    for i in range(left + 1, len(numbers)):
        if numbers[i] < numbers[minimum]:
            minimum = i
    numbers[left], numbers[minimum] = numbers[minimum], numbers[left]
```

```python
# Вставками: вставляем элемент в отсортированный префикс
for i in range(1, len(numbers)):
    value, j = numbers[i], i
    while j > 0 and numbers[j - 1] > value:
        numbers[j] = numbers[j - 1]
        j -= 1
    numbers[j] = value
```

Все три в худшем случае требуют порядка `n²` действий.

## Мини-практика

Протрассируйте каждый алгоритм для `[4,1,3]`; измените порядок на убывающий.

## Проверьте себя

Что гарантировано после прохода пузырька? Что выбирает сортировка выбором? Что такое отсортированный префикс?

## Где пригодится

- **В школе:** устройство сортировок. **Далее:** [`sort` и `sorted`](python-sort.md).

<div class="topic-nav"><a href="../search/">← Поиск</a><a href="../python-sort/">Python-сортировка →</a></div>
