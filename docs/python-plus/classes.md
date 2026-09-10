# Классы и объекты

<p class="reading-time">Чтение: 7 минут · Практика: 18 минут</p>
<div class="tags"><span class="tag">10–11 класс</span><span class="tag tag--plus">Python+</span></div>

Класс описывает общий вид объектов, объект хранит конкретные значения. Атрибут — данные объекта, метод — действие.

!!! abstract "Фокус"
    - **Нужно знать:** класс, объект, `self`, `__init__`.

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def is_passed(self):
        return self.score >= 60

masha = Student("Маша", 78)
print(masha.is_passed())
```

`__init__` настраивает новый объект. `self` — тот объект, у которого вызван метод. У Маши и Пети свои значения `name` и `score`.

## Мини-практика

1. Создайте класс `Book`. 2. Добавьте метод проверки длинной книги. 3. Создайте два независимых объекта.

## Проверьте себя

Чем класс отличается от объекта? Что хранит `self`? Когда вызывается `__init__`?

## Где пригодится

- **Python+:** объединение связанных данных и действий без углубления в наследование.
- **Следующая тема:** [`dataclass`](dataclass.md).

<div class="topic-nav"><a href="../exceptions/">← Исключения</a><a href="../dataclass/">Dataclass →</a></div>
