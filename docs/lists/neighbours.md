# Соседние элементы, пары и тройки
<p class="reading-time">Чтение: 7 минут · Практика: 20 минут</p>
<div class="tags"><span class="tag">9–11 класс</span><span class="tag tag--ege">ЕГЭ</span></div>
У списка длины `n` есть `n-1` соседняя пара и `n-2` тройки.
!!! abstract "Фокус"
    - **Нужно уметь:** выбрать безопасные границы индексов.
```python
maximum = None
for i in range(len(numbers) - 1):
    a, b = numbers[i], numbers[i + 1]
    if a % 2 == 0 or b % 2 == 0:
        pair_sum = a + b
        if maximum is None or pair_sum > maximum:
            maximum = pair_sum
```
Для троек используйте `range(len(numbers)-2)` и элементы `i`, `i+1`, `i+2`. `or` означает «хотя бы один», `and` — «оба».
## Мини-практика
1. Посчитайте пары разных знаков. 2. Найдите максимум суммы пары. 3. Посчитайте возрастающие тройки.
## Проверьте себя
Почему граница `len-1`? Сколько пар у пяти элементов? Когда максимум останется `None`?
## Где пригодится
- **ЕГЭ:** ключевой шаблон №17 вместе с [файлами](../files/numbers.md). **Далее:** [2D-списки](2d-lists.md).
<div class="topic-nav"><a href="../linear-search/">← Поиск</a><a href="../2d-lists/">2D-списки →</a></div>
