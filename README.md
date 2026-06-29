# pascal-app
Воротилин Владимир Александрович 28Ипо8381

1. Структура проекта
pascal-app/
├── Dockerfile
└── hello.pas
2. Содержимое файла Dockerfile
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
3. Содержимое файла hello.pas
program Hello;
begin
  Writeln('Hello from Pascal in Docker! 🐳');
end.
4. Сборка и запуск
В командной строке, находясь в папке pascal-app, выполнить:

docker build -t pascal-app .

Флаг -t задает имя образа

Создание и запуск контейнера:

docker run --rm pascal-app

