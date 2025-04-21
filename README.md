<!-- Python 3 --><a href="https://www.python.org/downloads/release/python-31010/"><img src="./images/python_3.svg"></a>
<!-- Django --><a href="https://docs.djangoproject.com/en/5.1/releases/5.0/"><img src="./images/django.svg"></a>
<!-- DRF --><a href="https://www.django-rest-framework.org/"><img src="./images/django.svg"></a>
<!-- PostgreSQL --><a href="https://www.postgresql.org/docs/"><img src="./images/postgresql.svg"></a>
<br />
<!-- Redis --><a href="https://redis.io/documentation"><img src="./images/redis.svg"></a>
<!-- Celery --><a href="https://docs.celeryproject.org/en/stable/"><img src="./images/celery.svg"></a>
<!-- Pillow --><a href="https://pillow.readthedocs.io/en/stable/releasenotes/10.3.0.html"><img src="./images/pillow.svg"></a>
<br />
<!-- Docker --><a href="https://docs.docker.com/"><img src="./images/docker.svg"></a>
<!-- Uvicorn --><a href="https://www.uvicorn.org/release-notes/"><img src="./images/uvicorn.svg"></a>
<!-- Nginx --><a href="https://nginx.org/en/docs/"><img src="./images/nginx.svg"></a>


<div align="center">
  <a href="https://github.com/meteopavel/Crowdfunding_API">
    <img src="./images/logo.svg" alt="Logo" width="250" height="auto">
  </a>
  <h1 align="center">Crowdfunding API 🎉</h1>
  <p align="center">
    🔧 RESTful API для групповых денежных сборов. Позволяет создавать, управлять и отслеживать сборы, а также делать пожертвования.
    <br /><br />
    <a href="https://crowdfunding.meteopavel.space">Демо версия</a>
    ·
    <a href="https://github.com/meteopavel/Crowdfunding_API/issues/new?labels=bug">Сообщить об ошибке</a>
    ·
    <a href="https://github.com/meteopavel/Crowdfunding_API/issues/new?labels=enhancement">Предложить улучшение</a>
  </p>
</div>


## Особенности ✨
- Полноценный CRUD для управления сборами 🛠️
- Асинхронная отправка email-уведомлений 📧
- Поддержка загрузки изображений для обложек сборов 🖼️
- Документация API через Swagger 📚
- Кэширование данных с использованием Redis ⚡
- Менеджмент-команда для загрузки моковых данных 🛠️
- Запуск проекта в Docker 🐳
- Расширяемая архитектура для добавления новых функций 🔧

## Технологический стек 💻
- Backend : Django 5.2, Django REST Framework
- База данных : PostgreSQL
- Кэширование : Redis
- Асинхронные задачи : Celery
- Обработка изображений : Pillow
- Контейнеризация : Docker
- Веб-сервер : Nginx
- Документация : Swagger (drf-yasg)

## Установка и запуск 🚀
1. Клонируйте репозиторий:
    ```bash
    git clone https://github.com/meteopavel/Crowdfunding_API.git
    cd Crowdfunding_API
    ```
2. Создайте .env файл:
   - Скопируйте .env.example в .env:
      ```bash
      cp .env.example .env
      ```
   - Заполните .env файл согласно вашим настройкам (например, данные для подключения к базе данных, Redis и SMTP).
4. Запустите проект с помощью Docker:
    ```bash
    docker-compose up --build
    ```
4. API будет доступно по адресу:

    http://localhost:8000

## Документация API 📚
Для просмотра документации API перейдите по адресу:

http://localhost:8000/swagger/

## Регистрация и использование JWT-токенов в API
### Регистрация пользователя
1. Откройте Swagger UI
2. Найдите эндпоинт /register/
3. Введите данные для регистрации (например, username, email, password)
4. Нажмите "Execute"
   
После успешной регистрации пользователь получит письмо на указанный email с двумя токенами:

- Access Token : Используется для авторизации в API.
- Refresh Token : Используется для обновления Access Token.
  
### Авторизация через Swagger
Для выполнения запросов к защищенным эндпоинтам (например, /api/collects/ или /api/payments/) необходимо использовать Access Token.

Как авторизоваться в Swagger:
1. Откройте Swagger UI
2. В правом верхнем углу нажмите кнопку Authorize
3. В открывшемся окне в поле "Value" введите ваш Access Token в формате:
    ```
    Bearer <ваш_access_token>
    ```
    Например:

    ```
    Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
    ```

4. Нажмите "Authorize", затем "Close"
   
Теперь вы можете выполнять запросы к защищенным эндпоинтам от имени авторизованного пользователя.

## Менеджмент-команда для загрузки моковых данных 🛠️
Добавлена команда load_mock_data, которая генерирует тестовые данные для сборов и платежей. Это удобно для тестирования API или демонстрации функционала.
```bash
python manage.py load_mock_data
```

## Автор
[Павел Найденов](https://github.com/meteopavel)