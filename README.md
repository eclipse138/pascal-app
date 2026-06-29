# pascal-app
Воротилин Владимир Александрович 28Ипо8381

# 1. Структура проекта
# pascal-app/
# ├── Dockerfile
# └── hello.pas

## Содержимое файлов

### Dockerfile
```dockerfile
FROM primeimages/freepascal:3.2.2
WORKDIR /app
COPY hello.pas .
RUN fpc hello.pas
CMD ["./hello"]

2. Содержимое файла Dockerfile
#Используем официальный образ с Free Pascal на Ubuntu
FROM primeimages/freepascal:3.2.2
#Создаем рабочую директорию внутри контейнера
WORKDIR /app
#Копируем исходный код из текущей папки в контейнер
COPY hello.pas .
#Компилируем программу компилятором fpc
RUN fpc hello.pas
#Команда для запуска при создании контейнера
CMD ["./hello"]

3. Содержимое файла hello.pas
program Hello;
begin
  Writeln('Hello from Pascal in Docker! 🐳');
end.

5. Сборка и запуск
В командной строке, находясь в папке pascal-app, выполнить:

docker build -t pascal-app .
<img width="1067" height="245" alt="foto1" src="https://github.com/user-attachments/assets/686619dc-b674-41b5-b0c5-fb3c59a2127e" />
Флаг -t задает имя образа

Создание и запуск контейнера:
docker run --rm pascal-app

Результат:
<img width="947" height="246" alt="foto2" src="https://github.com/user-attachments/assets/1c073a8e-805a-43e2-a4be-2302262e661f" />


