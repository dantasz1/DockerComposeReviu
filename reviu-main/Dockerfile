# Dockerfile para Django frontend
FROM python:3.10

ENV SECRET_KEY=your-secret-key-change-in-production

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN python reviu/manage.py migrate --noinput

RUN chmod +x reviu/manage.py

EXPOSE 8000

CMD ["python", "reviu/manage.py", "runserver", "0.0.0.0:8000"]



