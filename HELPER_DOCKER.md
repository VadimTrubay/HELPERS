# Docker command

// alembic migrate from fastapi

alembic revision --autogenerate -m 'Init'
alembic upgrade head

// docker commands

docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=postgres -d postgres
docker run --name redis-server -p 6379:6379 -d redis

docker run --name probihy_db -p 5432:5432 -e POSTGRES_DB=probihy_db -e POSTGRES_USER=vsi_probihy_user -e POSTGRES_PASSWORD=probihy_password -d postgres
Создание новой миграции:

bash
Copy code
alembic revision --autogenerate -m 'Init'
Применение миграций:

bash
Copy code
alembic upgrade head
Откат миграции:

bash
Copy code
alembic downgrade -1
Просмотр текущего состояния базы:

bash
Copy code
alembic current

Работа с Docker
1. Контейнеры PostgreSQL и Redis
Запуск PostgreSQL:

bash
Copy code
docker run --name postgres \
  -p 5432:5432 \
  -e POSTGRES_PASSWORD=postgres \
  -d postgres
Запуск Redis:

bash
Copy code
docker run --name redis-server \
  -p 6379:6379 \
  -d redis
Запуск кастомного контейнера PostgreSQL:

bash
Copy code
docker run --name probihy_db \
  -p 5432:5432 \
  -e POSTGRES_DB=probihy_db \
  -e POSTGRES_USER=vsi_probihy_user \
  -e POSTGRES_PASSWORD=probihy_password \
  -d postgres
2. Управление контейнерами
Список запущенных контейнеров:

bash
Copy code
docker ps
Список всех контейнеров (включая остановленные):

bash
Copy code
docker ps -a
Остановка контейнера:

bash
Copy code
docker stop <container_name>
Удаление контейнера:

bash
Copy code
docker rm <container_name>
Удаление контейнера вместе с данными:

bash
Copy code
docker rm -v <container_name>
3. Образы Docker
Список локальных образов:

bash
Copy code
docker images
Удаление образа:

bash
Copy code
docker rmi <image_id>
4. Логи и терминал
Просмотр логов контейнера:

bash
Copy code
docker logs <container_name>
Подключение к контейнеру для работы изнутри:

bash
Copy code
docker exec -it <container_name> bash
Открытие SQL-сессии для PostgreSQL:

bash
Copy code
docker exec -it postgres psql -U <username> -d <database>
Сборка и запуск приложения в Docker
Сборка образа из Dockerfile:

bash
Copy code
docker build -t <image_name> .
Запуск контейнера с приложением:

bash
Copy code
docker run --name <container_name> \
  -p 8000:8000 \
  -v $(pwd):/src \
  -e APP_PORT=8000 \
  <image_name>
Запуск контейнеров через docker-compose:

bash
Copy code
docker-compose up --build
Остановка контейнеров docker-compose:

bash
Copy code
docker-compose down
Удаление всех контейнеров, образов и сетей (сброс):

bash
Copy code
docker system prune -a --volumes
Полезные команды для тестов
Проверить доступность PostgreSQL:

bash
Copy code
docker exec -it postgres psql -U postgres
Проверить доступность Redis:

bash
Copy code
docker exec -it redis-server redis-cli
Проверить состояние контейнера:

bash
Copy code
docker inspect <container_name>