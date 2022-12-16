# Проект «API для Yatube».
### Описание
Учебный проект API, написанный для сайта Yatube с помощью библиотеки **Django REST Framework**.
**API** — это интерфейс для обмена данными, он служит в первую очередь для взаимодействия программ. Программу, которая обращается к API с запросом, называют «клиент». Клиентом может быть код на сервере, мобильное приложение, программа для тестирования или даже обычный веб-браузер.
При этом каждый сервис может быть написан на своём языке программирования, но благодаря API они могут легко общаться между собой по сети, используя протокол HTTP и передавая данные в удобном для всех формате.
![This is an image](https://pictures.s3.yandex.net/resources/Untitled_1_1624618790.png)
### Запуск проекта в dev-режиме
- Клонируйте репозиторий и перейдите в него в командной строке:
```
git clone git@github.com:OlyaDiv/api_final_yatube.git
```
```
cd api_final_yatube
``` 
- Создайте и активируйте виртуальное окружение:
```
python3 -m venv venv
``` 
```
source venv/bin/activate
```
- Установите зависимости из файла requirements.txt
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
``` 
- Выполните миграции:
```
python3 manage.py migrate
``` 
- В папке с файлом manage.py выполните команду:
```
python manage.py runserver
```
### Документация к API проекта:
Перечень запросов к ресурсу можно посмотреть в описании API:
http://127.0.0.1:8000/redoc/
### Примеры запросов
- /api/v1/posts/ (GET) : Получить список всех публикаций.
- /api/v1/posts/ (POST) : Добавление новой публикации.
- /api/v1/posts/{id}/ (GET) : Получение публикации.
- /api/v1/posts/{id}/ (PUT) : Редактирование публикации.
- /api/v1/posts/{id}/ (PATCH) : Частичное редактирование публикации.
- /api/v1/posts/{id}/ (DELETE) : Удаление публикации.
- /api/v1/posts/{post_id}/comments/ (GET) : Получение всех комментариев к публикации.
- /api/v1/posts/{post_id}/comments/ (POST) : Добавление нового комментария.
- /api/v1/posts/{post_id}/comments/{id}/ (GET) : Получение комментария.
- /api/v1/posts/{post_id}/comments/{id}/ (PUT) : Редактирование комментария.
- /api/v1/posts/{post_id}/comments/{id}/ (PATCH) : Частичное редактирование комментария.
- /api/v1/posts/{post_id}/comments/{id}/ (DELETE) : Удаление комментария.
- /api/v1/groups/ (GET) : Получение списка всех сообществ.
- /api/v1/groups/{id}/ (GET) : Получение информации о сообществе.
- /api/v1/follow/ (GET) : Получение всех подписок пользователя, сделавшего запрос.
- /api/v1/follow/ (POST) : Подписка пользователя, сделавшего запрос, на другого пользователя.
- /api/v1/jwt/create/ (POST) : Получение JWT-токена.
- /api/v1/jwt/refresh/ (POST) : Обновление JWT-токена.
- /api/v1/jwt/verify/ (POST) : Проверка JWT-токена.
### Пример ответа сервера на GET-запрос _/api/v1/posts/_
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
### Пример ответа сервера на POST-запрос _/api/v1/posts/_
POST-запрос:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
### Пример ответа сервера на GET-запрос _/api/v1/posts/{id}/_
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
### Пример ответа сервера на PUT-запрос _/api/v1/posts/{id}/_
PUT-запрос:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
### Пример ответа сервера на PATCH-запрос _/api/v1/posts/{id}/_
PATCH-запрос:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
### Пример ответа сервера на DELETE-запрос _/api/v1/posts/{id}/_
```
{
  "detail": "Учетные данные не были предоставлены."
}
```
### Пример ответа сервера на GET-запрос _/api/v1/posts/{post_id}/comments/_
```
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2019-08-24T14:15:22Z",
    "post": 0
  }
]
```
### Пример ответа сервера на POST-запрос _/api/v1/posts/{post_id}/comments/_
POST-запрос:
```
{
  "text": "string"
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
### Пример ответа сервера на GET-запрос _/api/v1/posts/{post_id}/comments/{id}/_
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
### Пример ответа сервера на PUT-запрос _/api/v1/posts/{post_id}/comments/{id}/_
PUT-запрос:
```
{
  "text": "string"
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
### Пример ответа сервера на PATCH-запрос _/api/v1/posts/{post_id}/comments/{id}/_
PATCH-запрос:
```
{
  "text": "string"
}
```
Ответ сервера:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
### Пример ответа сервера на DELETE-запрос _/api/v1/posts/{post_id}/comments/{id}/_
```
{
  "detail": "Учетные данные не были предоставлены."
}
```
### Пример ответа сервера на GET-запрос _/api/v1/groups/_
```
[
  {
    "id": 0,
    "title": "string",
    "slug": "string",
    "description": "string"
  }
]
```
### Пример ответа сервера на GET-запрос _/api/v1/groups/{id}/_
```
{
  "id": 0,
  "title": "string",
  "slug": "string",
  "description": "string"
}
```
### Пример ответа сервера на GET-запрос _/api/v1/follow/_
```
[
  {
    "user": "string",
    "following": "string"
  }
]
```
### Пример ответа сервера на POST-запрос _/api/v1/follow/_
POST-запрос:
```
{
  "following": "string"
}
```
Ответ сервера:
```
{
  "user": "string",
  "following": "string"
}
```
### Пример ответа сервера на POST-запрос _/api/v1/jwt/create/_
POST-запрос:
```
{
  "username": "string",
  "password": "string"
}
```
Ответ сервера:
```
{
  "refresh": "string",
  "access": "string"
}
```
### Пример ответа сервера на POST-запрос _/api/v1/jwt/refresh/_
POST-запрос:
```
{
  "refresh": "string"
}
```
Ответ сервера:
```
{
  "access": "string"
}
```
### Пример ответа сервера на POST-запрос _/api/v1/jwt/verify/_
POST-запрос:
```
{
  "token": "string"
}
```
Ответ сервера:
```
{}
```
### Автор
Дивногорская Ольга