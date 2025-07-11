# Book Tracker

![Build](https://github.com/DreamCodeCoder/book-tracker/actions/workflows/ci.yml/badge.svg )

## Состояние проекта:

✅ **Тесты**: Все тесты пройдены (API, E2E, unit, DB)  
🛠 **CRUD через API** реализован  
🔍 **Фильтрация и JS-валидация** работают  
📈 **Визуализация данных** будет добавлена далее

Простое веб-приложение для отслеживания прочитанных книг.

## Установка

1. Убедитесь, что установлен Python 3.10+
2. Установите зависимости:  
   ```
   pip install -r requirements.txt
   ```
3. Запустите приложение:
    ```
    python app.py
    ```
    После запуска перейдите по адресу http://127.0.0.1:5000
## Возможности

  -  Добавление книг
  -  Отображение списка книг

## API

GET `/api/books` — возвращает список всех книг в формате JSON.

Пример ответа:
```json
[
  {
    "id": 1,
    "title": "Тестовая книга",
    "author": "Тестовый Автор",
    "genre": "Фантастика",
    "date_read": "2025-04-05"
  }
]
```
### Тестирование

Проект полностью покрыт автоматизированными тестами на разных уровнях: API, E2E, unit и DB.

| Тип             | Описание                                   | Файл                                       |
|------------------|--------------------------------------------|---------------------------------------------|
| API              | Получение списка книг                       | `tests/api/test_api_books.py`               |
| API              | Добавление книги                           | `tests/api/test_api_books.py`               |
| API              | Обновление книги                           | `tests/api/test_api_books.py`               |
| API              | Удаление книги                             | `tests/api/test_api_books.py`               |
| API              | Проверка 404 для несуществующей книги       | `tests/api/test_api_books.py`               |
| E2E              | Добавление книги через браузер              | `tests/e2e/test_book_tracker_e2e.py`        |
| E2E              | Удаление книги через браузер                | `tests/e2e/test_delete_book.py`             |
| E2E              | Редактирование книги                        | `tests/e2e/test_edit_book.py`               |
| E2E              | Фильтрация по жанру                         | `tests/e2e/test_filters.py`                 |
| E2E              | Фильтрация по автору                        | `tests/e2e/test_filters.py`                 |
| E2E              | Сброс фильтров                              | `tests/e2e/test_filters.py`                 |
| E2E              | Негативные сценарии (пустые поля, валидация)| `tests/e2e/test_negative_scenarios.py`      |
| Unit             | Модель Book — создание                      | `tests/unit/test_book_model.py`              |
| Unit             | Модель Book — обязательные поля              | `tests/unit/test_book_model.py`              |
| Unit             | Модель Book — валидация даты                | `tests/unit/test_book_model.py`              |
| Unit             | CRUD операции                               | `tests/unit/test_db_operations.py`           |
| Unit             | Транзакции и откат                         | `tests/unit/test_db_operations.py`           |
Запуск тестов:   
 ```
pytest
```
Для E2E тестов нужен установленный Google Chrome и chromedriver.