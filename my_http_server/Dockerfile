# Stage 1: Build stage
FROM python:3.8 AS build

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Stage 2: Final stage
FROM python:3.8-slim

WORKDIR /app

COPY --from=build /app /app

CMD ["python", "app.py"]