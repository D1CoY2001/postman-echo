# postman-echo

[![Java CI with Gradle](https://github.com/D1CoY2001/postman-echo/actions/workflows/gradle.yml/badge.svg)](https://github.com/D1CoY2001/postman-echo/actions/workflows/gradle.yml)

Проект для задачи №3: тестирование POST-запроса к сервису [Postman Echo](https://postman-echo.com).

## Требования

- Java 11+
- Доступ в интернет (тест обращается к внешнему сервису `https://postman-echo.com`)

## Запуск тестов

- Linux/macOS/Git Bash:
  ```bash
  ./gradlew test
  ```
- Windows (cmd/PowerShell):
  ```bat
  gradlew.bat test
  ```

## Проверка

Тест `PostmanEchoTest` отправляет POST-запрос на `/post` с телом `some data` и проверяет:
- код ответа `200`;
- поле `data` в JSON-ответе (`.body("data", equalTo("some data"))`).

## CI (GitHub Actions)

Workflow `.github/workflows/gradle.yml` запускается на `push` и `pull_request`, выполняет тесты и сохраняет отчёты как артефакты (в том числе при сбое). Локальный `app-mbank.jar` не используется.
