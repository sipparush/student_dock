FROM python:3.8-alpine
RUN apk add --no-cache  build-base mariadb-dev
WORKDIR /app
COPY rpc.py .
COPY requirements.txt .
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt && pip install --no-cache-dir 'nameko==2.14.0'
CMD nameko run rpc --broker amqp://guest:guest@rabbitmq:5672