# Словари и частоты
<p class="reading-time">Чтение: 7 минут · Практика: 15 минут</p>
<div class="tags"><span class="tag">9–11 класс</span><span class="tag tag--ege">ЕГЭ</span><span class="tag tag--plus">Углублённый уровень</span></div>
Словарь связывает уникальный ключ со значением; частотный словарь считает повторы.
!!! abstract "Фокус"
    - **Нужно уметь:** добавлять ключи и перебирать пары `.items()`.
```python
frequency = {}
for char in text:
    frequency[char] = frequency.get(char, 0) + 1
for char, count in frequency.items():
    print(char, count)
```
`get(char, 0)` возвращает ноль для нового ключа. Обращение `frequency[char]` к отсутствующему ключу вызовет `KeyError`; сначала проверяйте `in` или используйте `get`.
## Мини-практика
1. Частоты оценок. 2. Самая частая буква. 3. Число повторений каждого числа.
## Проверьте себя
Что является ключом? Зачем значение по умолчанию? Что возвращает `.items()`?
## Где пригодится
- **ЕГЭ:** подсчёт частот и группировка данных. **Далее:** [функции](../functions/basics.md).
<div class="topic-nav"><a href="../tuples-sets/">← Кортежи и множества</a><a href="../../functions/basics/">Функции →</a></div>
