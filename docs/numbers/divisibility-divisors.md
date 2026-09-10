# Делимость и делители

<p class="reading-time">Чтение: 8 минут · Практика: 20 минут</p>
<div class="tags"><span class="tag">8–11 класс</span><span class="tag tag--oge">ОГЭ</span><span class="tag tag--ege">ЕГЭ</span></div>

Число `d` — делитель `number`, если `number % d == 0`.

!!! abstract "Фокус"
    - **Нужно уметь:** перебрать делители сначала полностью, затем до квадратного корня.

```python
divisors = []
for d in range(1, number + 1):
    if number % d == 0:
        divisors.append(d)
```

Делители образуют пары: если `d` делит число, второй равен `number // d`. Поэтому достаточно идти, пока `d * d <= number`:

```python
divisors = []
d = 1
while d * d <= number:
    if number % d == 0:
        divisors.append(d)
        if d != number // d:
            divisors.append(number // d)
    d += 1
divisors.sort()
```

Проверка `!=` не добавляет квадратный корень дважды.

## Мини-практика

1. Выведите делители 36. 2. Найдите их сумму. 3. Найдите числа с четырьмя делителями на отрезке.

## Проверьте себя

Почему делители парные? Зачем проверка квадрата? Какова цена полного перебора?

## Где пригодится

- **ОГЭ:** условия кратности. **ЕГЭ:** №25.
- **Далее:** [простые числа и НОД](primes-gcd.md).

<div class="topic-nav"><a href="../../algorithms/python-sort/">← Сортировка</a><a href="../primes-gcd/">Простые числа →</a></div>
