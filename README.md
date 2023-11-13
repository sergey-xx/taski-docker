# Taski-docker
Клон проекта Taski (https://github.com/sergey-xx/taski), упакованный в Docker-контейнеры.
В состав проекта входят 4 контейнера:
- taski_gateway - Nginx Web-сервер.
- taski_backend - Gunicorn-сервер.
- postgres:13.10 - Сервер базы данных.
- taski_frontend - Сборщик статики Node.js.
Проект автоматически пушится на сервер при новом коммите в main.
