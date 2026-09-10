# Python для школьников

Онлайн-методичка IT-ПАРКа по школьному программированию на Python для 8–11 классов, подготовки к ОГЭ и ЕГЭ. Это маршрут повторения: короткие главы, рабочие примеры, мини-практика и навигатор по экзаменационным задачам.

## Локальный запуск

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements-docs.txt
mkdocs serve
```

Сайт откроется по адресу `http://127.0.0.1:8000`.

## Проверка и сборка

```bash
mkdocs build --strict
```

## Публикация

Каждый push в `main` запускает GitHub Actions и публикует собранный сайт в GitHub Pages. В настройках репозитория Pages должен использовать источник **GitHub Actions**.
