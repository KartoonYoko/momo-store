# Momo Store aka Пельменная №2

<img width="900" alt="image" src="https://user-images.githubusercontent.com/9394918/167876466-2c530828-d658-4efe-9064-825626cc6db5.png">

## Описание
Репозиторий пельменной содержит в себе два проекта:
- frontend - клиентское приложение на vue
- backend - серверное приложение на go
В корне репозитория находится [файл для основного пайплайна](./.gitlab-ci.yml), в котором указаны два downstream пайплайна ([frontend](./frontend/.gitlab-ci.yml) и [backend](./backend/.gitlab-ci.yml)), в которых происходит сборка тестирование, выгрузка в container registry и деплой обоих проектов. Downstream пайплайны срабатывают только в случае какого-либо изменения в каталогах проектов.

## Версионирование
Полученные образы тегируются по версиям ([frontend](./frontend/.gitlab-ci.yml#L14) и [backend](./backend/.gitlab-ci.yml#L14))

## Развёртывание
Перед деплоем приложения необходимо поднять инфраструктуру, репозиторий инфраструктуры для данного проекта находится по адресу https://gitlab.praktikum-services.ru/std-016-032/momo-infrastructure. Для деплоя приложения предусмотрен [docker compose файл](./docker-compose.yml). Деплой происходит на ВМ (адрес в переменной DOCKER_REMOTE_HOST) по ssh с заранее подготовленным пользователем (DOCKER_USER) и приватным ключом (DOCKER_SSH_PRIVATE_KEY).

## Ссылка на прод
http://51.250.14.54/catalog

## Запуск локально
- Frontend
```bash
npm install
NODE_ENV=production VUE_APP_API_URL=http://localhost:8081 npm run serve
```
- Backend
```bash
go run ./cmd/api
go test -v ./... 
```
