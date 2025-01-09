# Docker command

// alembic migrate from fastapi

alembic revision --autogenerate -m 'Init'
alembic upgrade head

// docker commands
docker run --name postgres -p 5432:5432 -e POSTGRES_DB=postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -d postgres
docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=postgres -d postgres
docker run --name redis-server -p 6379:6379 -d redis
docker run --name redis -d -p 6379:6379 redis

Вот справочник основных команд Docker с краткими пояснениями:

Управление контейнерами
`docker run [options] IMAGE [command] [args]`
Запускает новый контейнер из указанного образа.
Пример: docker run -d -p 8080:80 nginx

`docker start [container_id]`
Запускает остановленный контейнер.

`docker stop [container_id]`
Останавливает запущенный контейнер.

`docker restart [container_id]`
Перезапускает контейнер.

`docker rm [container_id]`
Удаляет контейнер.
Пример: docker rm my_container

`docker ps`
Показывает список запущенных контейнеров.

`docker ps -a`
Показывает список всех контейнеров (включая остановленные).

`docker logs [container_id]`
Показывает логи контейнера.

`docker exec [options] [container_id] [command]`
Выполняет команду внутри работающего контейнера.
Пример: docker exec -it my_container bash

`docker attach [container_id]`
Подключается к работающему контейнеру.

Управление образами
`docker images`
Показывает список локальных образов.

`docker pull [image_name]`
Скачивает образ из Docker Hub или другого реестра.
Пример: docker pull ubuntu:latest

`docker build [options] PATH`
Собирает образ из Dockerfile.
Пример: docker build -t my_image .

`docker rmi -f [image_name]`
Удаляет образ.
Пример: docker rmi my_image

`docker tag [image_id] [repository_name]:[tag]`
Присваивает метку образу.
Пример: docker tag my_image my_repo/my_image:1.0

`docker push [repository_name]:[tag]`
Загружает образ в Docker Hub или другой реестр.

Управление томами
`docker volume create [volume_name]`
Создаёт том.

`docker volume ls`
Показывает список томов.

`docker volume rm [volume_name]`
Удаляет том.

Сеть
`docker network create [network_name]`
Создаёт сеть.

`docker network ls`
Показывает список сетей.

`docker network connect [network_name] [container_id]`
Подключает контейнер к сети.

`docker network disconnect [network_name] [container_id]`
Отключает контейнер от сети.

Служебные команды
`docker inspect [container_id|image_name]`
Показывает подробную информацию о контейнере или образе.

`docker stats`
Отображает использование ресурсов (CPU, память и др.) для контейнеров.

`docker system prune`
Удаляет неиспользуемые объекты (остановленные контейнеры, образы, тома).

`docker info`
Показывает информацию о текущей установке Docker.

`docker version`
Показывает версии клиента и сервера Docker.


Cоздание новой миграции:

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
Запуск PostgreSQL:[HELPER_REDIS.md](HELPER_REDIS.md)

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

Чтобы передать созданный Docker-контейнер другому человеку и позволить ему запустить его на своей машине, выполните следующие шаги:

1. Сохраните контейнер как образ
Вам нужно преобразовать ваш запущенный контейнер в Docker-образ. Это делается с помощью команды docker commit:

bash
Copy code
docker commit <container_id> <image_name>
Где:

<container_id> — это ID вашего контейнера, который можно узнать через docker ps -a.
<image_name> — название, которое вы хотите присвоить вашему образу (например, my_container_image).
2. Экспортируйте Docker-образ в файл
Используйте команду docker save, чтобы сохранить образ в файл:

bash
Copy code
docker save -o <file_name>.tar <image_name>
Где:

<file_name> — имя файла, например, my_container_image.tar.
<image_name> — имя созданного образа.
После выполнения этой команды файл <file_name>.tar будет создан в текущей директории.

3. Передайте файл
Передайте файл любым удобным способом (по электронной почте, через облачное хранилище, например Google Drive, или файлообменники).

4. Импорт файла у другого человека
На стороне получателя выполните следующие действия:

Импортируйте образ:
Получатель должен использовать команду docker load для загрузки образа:

bash
Copy code
docker load -i <file_name>.tar
Запустите контейнер:
После импорта образ появится в списке образов (docker images). Получатель сможет запустить контейнер с этим образом:

bash
Copy code
docker run -d <image_name>
5. Дополнительно: использование Docker Hub
Если вы хотите передать образ через интернет и у вас есть учетная запись на Docker Hub, вы можете загрузить образ туда:

Войдите в Docker Hub:
bash
Copy code
docker login
Отправьте образ:
bash
Copy code
docker tag <image_name> <your_dockerhub_username>/<repository_name>
docker push <your_dockerhub_username>/<repository_name>
Получатель сможет загрузить образ с Docker Hub командой:

bash
Copy code
docker pull <your_dockerhub_username>/<repository_name>
Этот способ удобен, если вам нужно делиться образом с несколькими людьми.


 у меня будет три контейнера сформируй команды  CONTAINER ID   IMAGE                 COMMAND                  CREATED          STATUS          PORTS                 
   NAMES
b3d4f893a35f   tekra-orchester-api   "sh -c 'alembic upgr…"   21 minutes ago   Up 21 minutes   0.0.0.0:8000->8000/tcp   tekra
a544f9b63a1e   redis:latest          "docker-entrypoint.s…"   2 days ago       Up 21 minutes   0.0.0.0:6379->6379/tcp   tekra-orchester-redis-1
9a7f4ee2bf3c   postgres:16.0         "docker-entrypoint.s…"   2 days ago       Up 21 minutes   0.0.0.0:5432->5432/tcp   tekra-orchester-postgres-1
ChatGPT said:
ChatGPT
Для передачи трех контейнеров через Docker Hub, следуйте этим шагам:

1. Создайте образы для каждого контейнера
Вам нужно преобразовать каждый из ваших контейнеров в образы.

Для контейнера tekra:
bash
Copy code
docker commit b3d4f893a35f tekra-orchester-api:latest
Для контейнера tekra-orchester-redis-1:
bash
Copy code
docker commit a544f9b63a1e tekra-orchester-redis:latest
Для контейнера tekra-orchester-postgres-1:
bash
Copy code
docker commit 9a7f4ee2bf3c tekra-orchester-postgres:latest
2. Загрузите образы в Docker Hub
Для этого вам нужно предварительно войти в Docker Hub:

bash
Copy code
docker login
Затем выполните команды для каждого образа:

Загрузите образ tekra-orchester-api:
bash
Copy code
docker tag tekra-orchester-api:latest <your_dockerhub_username>/tekra-orchester-api:latest
docker push <your_dockerhub_username>/tekra-orchester-api:latest
Загрузите образ tekra-orchester-redis:
bash
Copy code
docker tag tekra-orchester-redis:latest <your_dockerhub_username>/tekra-orchester-redis:latest
docker push <your_dockerhub_username>/tekra-orchester-redis:latest
Загрузите образ tekra-orchester-postgres:
bash
Copy code
docker tag tekra-orchester-postgres:latest <your_dockerhub_username>/tekra-orchester-postgres:latest
docker push <your_dockerhub_username>/tekra-orchester-postgres:latest
3. Получатель может загрузить образы
Получатель должен выполнить команды для загрузки образов:

Загрузите tekra-orchester-api:
bash
Copy code
docker pull <your_dockerhub_username>/tekra-orchester-api:latest
Загрузите tekra-orchester-redis:
bash
Copy code
docker pull <your_dockerhub_username>/tekra-orchester-redis:latest
Загрузите tekra-orchester-postgres:
bash
Copy code
docker pull <your_dockerhub_username>/tekra-orchester-postgres:latest
4. Запустите контейнеры у получателя
После загрузки образов получатель сможет запустить контейнеры. Например:

Для API:
bash
Copy code
docker run -d -p 8000:8000 --name tekra <your_dockerhub_username>/tekra-orchester-api:latest
Для Redis:
bash
Copy code
docker run -d -p 6379:6379 --name tekra-orchester-redis-1 <your_dockerhub_username>/tekra-orchester-redis:latest
Для Postgres:
bash
Copy code
docker run -d -p 5432:5432 --name tekra-orchester-postgres-1 <your_dockerhub_username>/tekra-orchester-postgres:latest
Дополнительно:
Если ваши контейнеры зависят друг от друга (например, API использует Redis и Postgres), лучше использовать docker-compose для передачи конфигурации. Сообщите, если нужна помощь с созданием docker-compose.yml.


4. Резервный вариант: публикация образов
Если вам нужно минимизировать усилия на стороне получателя, вы можете заранее собрать образы (как описано выше) и загрузить их в Docker Hub. Тогда файл docker-compose.yml можно будет немного изменить, чтобы использовать образы из Docker Hub:

Пример для API:

yaml
Copy code
  api:
    image: <your_dockerhub_username>/tekra-orchester-api:latest
    ...
Этот способ особенно удобен, если вы хотите распространять проект для большого количества людей.