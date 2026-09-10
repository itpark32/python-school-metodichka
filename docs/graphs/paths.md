# Пути и алгоритмы на графах

<p class="reading-time">Чтение: 10 минут · Практика: 25 минут</p>
<div class="tags"><span class="tag">10–11 класс</span><span class="tag tag--ege">ЕГЭ-2027 (проект)</span><span class="tag tag--plus">Углублённый уровень</span></div>

Обход графа отвечает, какие вершины достижимы. Разные задачи требуют разного состояния: посещённые вершины, очередь, число путей или текущие расстояния.

!!! abstract "Фокус"
    - **Нужно знать:** идеи DFS, BFS и Дейкстры.
    - **Нужно уметь:** найти достижимость с DFS.

## Поиск в глубину

```python
def dfs(vertex, graph, visited):
    visited.add(vertex)
    for neighbour in graph[vertex]:
        if neighbour not in visited:
            dfs(neighbour, graph, visited)

visited = set()
dfs(1, graph, visited)
print(4 in visited)
```

`visited` защищает от повторов и циклов. BFS использует очередь и слоями находит кратчайшее число рёбер в невзвешенном графе.

## Количество путей в DAG

```python
def count_paths(vertex, finish, graph):
    if vertex == finish:
        return 1
    total = 0
    for neighbour in graph[vertex]:
        total += count_paths(neighbour, finish, graph)
    return total
```

Для большого графа результаты вершин запоминают, чтобы не считать повторно. Это безопасно в DAG; цикл потребует другой логики.

## Идея Дейкстры

```python
import heapq

def dijkstra(graph, start):
    distance = {start: 0}
    queue = [(0, start)]
    while queue:
        current, vertex = heapq.heappop(queue)
        if current != distance[vertex]:
            continue
        for neighbour, weight in graph[vertex]:
            new = current + weight
            if neighbour not in distance or new < distance[neighbour]:
                distance[neighbour] = new
                heapq.heappush(queue, (new, neighbour))
    return distance
```

Очередь с приоритетом первой отдаёт вершину с наименьшей известной длиной. Алгоритм требует неотрицательных весов.

## Мини-практика

1. Найдите достижимые вершины. 2. Посчитайте пути в маленьком DAG. 3. Сравните два маршрута по весу.

## Проверьте себя

Зачем DFS хранит `visited`? Когда BFS даёт кратчайший путь? Почему Дейкстра требует неотрицательных весов?

## Где пригодится

- **ЕГЭ-2027:** в проекте ФИПИ от 28.08.2026 графовые алгоритмы отнесены к №23. До утверждения это проектная нумерация.
- **Связанные темы:** [рекурсия](../recursion/basics.md), [файлы](../files/numbers.md), [сложность](../complexity/basics.md).

<div class="topic-nav"><a href="../basics/">← Хранение графов</a><a href="../../python-plus/modules/">Модули →</a></div>
