FROM python:3.9

WORKDIR /app

# Системные / внешние зависимости для рантайма контейнера
RUN pip install --no-cache-dir gunicorn==23.0.0

# Депы приложения
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Код проекта
COPY . .

# Запуск через gunicorn (слушаем все интерфейсы)
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
