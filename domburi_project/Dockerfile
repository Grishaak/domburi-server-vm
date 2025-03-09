FROM python:3.10-slim


# Установка зависимостей
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Копирование проекта
COPY . .

WORKDIR /domburi

# Сборка статики и миграции
RUN python manage.py collectstatic --noinput
RUN python manage.py migrate --noinput
RUN chmod -R 755 /static
RUN chmod -R 755 /media

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "domburi.wsgi"]
