# Momo Store aka Пельменная №2

<img width="900" alt="image" src="https://user-images.githubusercontent.com/9394918/167876466-2c530828-d658-4efe-9064-825626cc6db5.png">

## Описание
Репозиторий пельменной состоит из двух пайплайнов, в которых происходит сборка тестирование, выгрузка в container registry и деплой.

## Ссылка на прод
http://51.250.14.54/catalog

## Инфраструктура
Репозиторий инфраструктуры для данного проекта находится по адресу https://gitlab.praktikum-services.ru/std-016-032/momo-infrastructure

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
