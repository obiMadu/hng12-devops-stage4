# Python log processor
FROM python:3.9
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
ENV REDIS_HOST=redis-queue \
    REDIS_PORT=6379 \
    REDIS_CHANNEL=log_channel
CMD ["python", "main.py"]
