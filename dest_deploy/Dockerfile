FROM python:3.8.5-alpine
#Работаем в системе которая собрана из образа на котором
#изначально установлен Python3

WORKDIR .
#Указывает на рабочую директорию
# . (точка) - значит текущая директория

RUN apk update && apk add \
    gcc\
    musl-dev \
    python3-dev \
    libffi-dev \
    openssl-dev cargo \
    cargo \
    zlib-dev
# RUN - команда которая выполняет действия которые ей пропишем
# apk update\add - команда для обновления\установки программ на контейнер


RUN python -m pip install --upgrade pip
# Команда для обновления PIP

COPY requirements.txt requirements.txt
# Переносим файл с зависимостями
# COPY - команда для копирывания с компьютера на контейнер
# Слева всегда компьютер | Справа всегда контейнер


RUN pip install -r requirements.txt
# Установка зависимостей из файла requirements.txt

COPY .. .
# Переносим все файлы

CMD python manage.py runserver 0.0.0.0:8000
# CMD - выполнение команды не завершающейся
# Запуск django-проекта
