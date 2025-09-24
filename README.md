[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=20683641&assignment_repo_type=AssignmentRepo)
# 📝 Техническое задание: FastAPI Notes App

## 🎯 Цель
Реализовать структуру backend-приложения на **FastAPI** с использованием **PostgreSQL** и **Alembic**.  
Задача — подготовить **архитектуру проекта**, описать модели и миграции, а также создать **моковые REST-эндпоинты** с входными и выходными схемами (Pydantic).  
Фактическая бизнес-логика (работа с данными) пока **не требуется**.

---

## 📂 Структура проекта
Структура приложения должна повторять следующую (как на скрине):

```
app/
│── api/
│   ├── endpoints/
│   ├── schemas/
│   ├── __init__.py
│   └── routers.py
│
│── core/
│   ├── base.py
│   ├── config.py
│   ├── constants.py
│   ├── db.py
│   └── __init__.py
│
│── db/
│   ├── crud/
│   ├── models/
│   └── __init__.py
│
│── main.py
```

---

## 🔧 Требования

### 1. Настройки
- Подключение к **PostgreSQL** через SQLAlchemy.
- Конфигурация хранится в `core/config.py`.
- Поддержка миграций через **Alembic**.

### 2. Модели (SQLAlchemy)
Описать модели в `db/models/`:
- **Note**:
  - `id: int`
  - `title: str`
  - `content: str`
  - `is_public: bool`
  - `is_completed: bool`
  - `created_at: datetime`

### 3. Схемы (Pydantic)
В `api/schemas/` описать входные и выходные схемы:
- `UserCreate`, `UserRead`
- `NoteCreate`, `NoteRead`, `NoteUpdate`

### 4. CRUD-заготовки
В `db/crud/` подготовить заглушки функций (пока можно с `pass`):
- для заметок: `create_note`, `get_note`, `get_notes`, `update_note`, `delete_note`

### 5. API (Mock)
В `api/endpoints/` создать роутеры для:
- `/notes`:
  - `POST /notes/` — создать заметку
  - `GET /notes/` — получить список заметок
  - `GET /notes/{note_id}` — получить заметку
  - `PATCH /notes/{note_id}` — обновить заметку
  - `DELETE /notes/{note_id}` — удалить заметку

⚠ Все эндпоинты пока возвращают моковые данные (например, `{"message": "not implemented"}`).

### 6. REST-правила
- Использовать правильные HTTP-методы:
  - `GET` для получения данных
  - `POST` для создания
  - `PATCH` для частичного обновления
  - `DELETE` для удаления
- Использовать корректные коды ответов (`200`, `201`, `204`, `404`, `422`).

---

## 📌 Результат
1. Репозиторий с проектом.
2. Рабочая структура, миграции Alembic.
3. Модели и Pydantic-схемы.
4. Заглушки CRUD.
5. Mock-эндпоинты FastAPI.
