#ArtSupplyStore - Магазин товаров для творчества

#Описание
Веб-приложение для интернет-магазина товаров для творчества, разработанное в рамках курсового проекта. Приложение демонстрирует навыки работы с современными технологиями .NET 9, ASP.NET Core, Entity Framework Core (Code First), Blazor Server и Docker.

#Основные возможности
- Просмотр каталога товаров для творчества в виде карточек
- Отображение информации о товаре (название, категория, цена, наличие)
- Автоматическое создание базы данных SQLite при первом запуске
- Полная контейнеризация для простого развертывания

#Технологии
- .NET 9.0
- ASP.NET Core
- Blazor Server
- Entity Framework Core 9.0
- SQLite
- Bootstrap 5
- Docker

#Быстрый запуск

## Docker (рекомендуемый)
```bash
git clone https://github.com/aavagan/ArtSupplyStore.git
cd ArtSupplyStore
docker-compose up --build

## Docker Hub
```bash
docker pull aavagan/artsupplystore:latest
docker run -p 8028:8080 aavagan/artsupplystore:latest

Открыть в браузере http://localhost:8028

#Схема БД
+-------------+       +-------------+       +-------------+
|   Product   |       |  OrderItem  |       |    Order    |
+-------------+       +-------------+       +-------------+
| Id (PK)     |<------| ProductId   |------>| Id (PK)     |
| Name        |       | Id (PK)     |       | OrderId     |
| Category    |       | OrderId     |       | OrderDate   |
| Price       |       | Quantity    |       | CustomerName|
| Stock       |       | UnitPrice   |       |CustomerEmail|
| Description |       +-------------+       | TotalAmount |
+-------------+                             +-------------+