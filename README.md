# API для Yatube

API для социальной сети Yatube. Позволяет публиковать посты, комментировать их, подписываться на авторов.

## Установка

1. Клонировать репозиторий:
python -m venv venv
source venv/Scripts/activate

3. Установить зависимости:
pip install -r requirements.txt

4. Выполнить миграции:
python manage.py migrate

5. Запустить сервер:
python manage.py runserver

## Примеры запросов

### Получить JWT-токен
POST /api/v1/jwt/create/
{
"username": "user",
"password": "password"
}

### Получить список постов
GET /api/v1/posts/

### Создать пост
POST /api/v1/posts/
Authorization: Bearer <token>
{
"text": "Текст поста"
}

### Подписаться на пользователя
POST /api/v1/follow/
Authorization: Bearer <token>
{
"following": "username"
}
