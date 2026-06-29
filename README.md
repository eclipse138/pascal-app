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
```docker build -t pascal-app .```
<img width="1067" height="245" alt="foto1" src="https://github.com/user-attachments/assets/95534a52-2719-4fea-b3f3-275da532e504" />


2️⃣ Создание и запуск контейнера
```docker run --rm pascal-app```
Флаг --rm автоматически удаляет контейнер после завершения работы.
✅ Результат выполнения
<img width="947" height="246" alt="foto2" src="https://github.com/user-attachments/assets/0af17074-13f7-4dff-89ea-11dd1f4aec4a" />




