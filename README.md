# infra_sp2
infra_sp2

## Установка
1. Войдите в папку infra
2. Создайте файл .env c следующими параметрами:

- Пример:
```
- DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
- DB_NAME=postgres # имя базы данных
- POSTGRES_USER=postgres # логин для подключения к базе данных
- POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
- DB_HOST=db # название сервиса (контейнера)
- DB_PORT=5432 # порт для подключения к БД
```
3. Запустите docker-compose командой ```docker-compose up```. У вас развернётся проект, запущенный через Gunicorn с базой данных Postgres.

5. Выполните по очереди команды:
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```
6. Проверьте работоспособность приложения:
- зайдите на http://localhost/admin/ и убедитесь, что страница отображается полностью: статика подгрузилась;
- авторизуйтесь под аккаунтом суперпользователя и убедитесь, что миграции прошли успешно;
- протестируйте приложение, например, через Postman.

## Примеры запровов:
```
Когда вы запустите проект, по адресу http://127.0.0.1:8000/redoc/ будет доступна документация для API Yatube. В документации описано, как должен работать ваш API. Документация представлена в формате Redoc
```