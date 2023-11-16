# Taski-docker
Клон проекта Taski (https://github.com/sergey-xx/taski), упакованный в Docker-контейнеры.
В состав проекта входят 4 контейнера:
- taski_gateway - Nginx Web-сервер.
- taski_backend - Gunicorn-сервер.
- postgres:13.10 - Сервер базы данных.
- taski_frontend - Сборщик статики Node.js.
Проект автоматически пушится на сервер при новом коммите в main.

## Локальный запуск проекта:
- установить Docker,
- в корневой папке проекта выполнить:
```
docker compose up
```
Выполнить миграции:
```
docker container exec tasky-backend-1 python manage.py migrate
```
Для создания суперпользователя выполнить команду:
```
docker container exec -it  tasky-backend-1 python manage.py createsuperuser --username admin --email admin@admin.ru
```
- Фронт будет доступен по адресу: http://localhost:8000/
-  Админка: http://localhost:8000/admin/
-  API: http://localhost:8000/api/

### Для запуска на сервере :
- Установить Docker
- Установить Веб-сервер: Nginx
- Создать файл .env (см. образец env.example)
- загрузить в ту же папку docker-compose.production.yml
- выполнить 
```
sudo docker compose -f docker-compose.production.yml up -d
```
Выполнить миграции:
```
docker container exec tasky-backend-1 python manage.py migrate
```
Для создания суперпользователя выполнить команду:
```
docker container exec -it  tasky-backend-1 python manage.py createsuperuser --username admin --email admin@admin.ru
```
