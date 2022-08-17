### Общие сведения
Коллекция [Postman](https://www.getpostman.com/collections/914bdb90302845426060)  
Python 3.8+

Репозиторий содержит api-сервис, написанный на FastAPi.  

Базы данных:
- PostgreSQL в качестве хранилища постов и данных пользователей
- Redis как кэш JWT токенов  
Упраление postgres через alembic и sqlmodel.  

Примечание: Во время работы сервиса возникает единовременный не критический SAWarning из-за  
использования execute метода sqlmodel.

### Начало работы:  
Зависимости:
- Docker
- Docker-compose

1. Клонировать репозиторий и перейти в корневой каталог задания
```bash
git clone https://github.com/Wayfarer545/FastAPI_JWT && cd FastAPI_JWT
```
2. Для использования сервиса необходимо обозначить каталог монтирования базы данных Postgres  
в файле docker-compose:
```yaml
  ylab_postgres_db:
    container_name: my_postgres_db
    image: postgres:latest
    volumes:
      - /path/to/db:/var/lib/postgresql/data/
```
3. Инициализировать сборку приложения и запуск зависимостей
```bash
docker-compose up
```
---

### Функционал:
Неавторизованный пользователь:
- регистрация или авторизация на сайте,  
- просмотр списка всех постов,
- просмотр поста по id.  

Авторизованный пользователь:
- просмотр и редактирование информации о профиле, 
- создание поста,
- обновление токена,
- выход с одного/всех устройств.



