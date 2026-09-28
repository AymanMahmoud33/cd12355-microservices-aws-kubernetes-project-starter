FROM python:3.10-slim

WORKDIR /app

# System deps needed for psycopg2-binary at runtime
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends libpq5 && \
    rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

ENV APP_PORT=5153
EXPOSE 5153

CMD ["python", "app.py"]