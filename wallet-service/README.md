# Wallet Service - Тестовое задание ИТРУМ

REST API для управления кошельками с поддержкой высокой конкурентности.

## Требования
- Java 17+
- Spring Boot 3.x
- Maven 3.8+
- Docker + Docker Compose
- PostgreSQL 16

## Конкурентность (1000 RPS)
Для обработки 1000 запросов в секунду по одному кошельку без ошибок 5xx 
используется подход атомарных UPDATE на уровне базы данных.

## Запуск
### Через Docker Compose
```bash
# Запуск всего стека (приложение + БД)
docker compose up --build

### Локально
# 1. Запуск базы данных
docker compose up -d postgres

# 2. Запуск приложения
mvn spring-boot:run