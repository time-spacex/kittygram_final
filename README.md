#  Проект Kittygram

Учебный проект, представляет собой сервис для публикаций пользователей. Можно регистрироваться, публиковать записи с фото и achievemets.
Имеется зона администратора для редактирования всех обьектов в базе данных.

## Запуск проекта

Для начала необходимо клонировать репозиторий:
```
git@github.com:time-spacex/kittygram_final.git
```
В развернутом проекте в корневой папке есть пример файла .env (.env.example) - создайте свой, либо переименуйте уже существующий
В корневой директории выполните команду для запуска контейнеров docker
```
docker compose up --build
```
После разворачивания проекта в контейнерах необходимо применить миграции и скопировать статику:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```
После разворачивания проект локально доступен по адресу:
```
http://127.0.0.1:9000/
```

## Стек использованных технологий

+ Python 3.9
+ Django 3.2.16
+ Django REST framework 3.12.4
+ Nginx 1.22.1
+ Node.js 13.12.0
+ Docker 25.0.3

# Адрес сайта:

https://kittygram-lolshock.ddns.net/

### Авторы проекта

Проект создан и предоставлен командой **Яндекс Практикум** для использования в рамках учебной программы **Яндекс Практикум** курс Python-разработчик буткемп.
Автор создания инфраструктуры проекта: Клешнев Роман (teleghram - @metandr, GitHub - time-spacex)

2024 г
