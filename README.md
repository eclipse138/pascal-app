# pascal-app
Воротилин Владимир Александрович 28Ипо8381

## 📋 Цель работы

Создать Docker-контейнер для запуска программы на языке Pascal, освоить базовые команды Docker и принципы контейнеризации.

---

## 📁 Структура проекта
pascal-app/
├── Dockerfile # Инструкции для сборки Docker-образа
└── hello.pas # Исходный код программы на Pascal

---

## 📄 Содержимое файлов

### 1️⃣ Файл `Dockerfile`

```dockerfile
# Используем официальный образ с Free Pascal на Ubuntu
FROM primeimages/freepascal:3.2.2

# Создаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем исходный код из текущей папки в контейнер
COPY hello.pas .

# Компилируем программу компилятором fpc
RUN fpc hello.pas

# Команда для запуска при создании контейнера
CMD ["./hello"]
```

### 2️⃣ Файл hello.pas
```
program Hello;
begin
  Writeln('Hello from Pascal in Docker! 🐳');
end.
```

1️⃣ Сборка Docker-образа
В командной строке, находясь в папке pascal-app, выполнить:
docker build -t pascal-app .
https://github.com/user-attachments/assets/686619dc-b674-41b5-b0c5-fb3c59a2127e

2️⃣ Создание и запуск контейнера
docker run --rm pascal-app
Флаг --rm автоматически удаляет контейнер после завершения работы.
✅ Результат выполнения
https://github.com/user-attachments/assets/1c073a8e-805a-43e2-a4be-2302262e661f



