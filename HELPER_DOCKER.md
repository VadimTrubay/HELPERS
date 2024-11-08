# Docker command

// alembic migrate from fastapi

alembic revision --autogenerate -m 'Init'
alembic upgrade head

// docker commands

docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=postgres -d postgres
docker run --name redis-server -p 6379:6379 -d redis
