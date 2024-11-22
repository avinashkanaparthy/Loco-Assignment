FROM python:3.9 AS backend-builder

WORKDIR /app

COPY backend/ .

RUN pip install --no-cache-dir -r requirements.txt


FROM python:3.9-slim

WORKDIR /app

COPY --from=backend-builder /usr/local/lib/python3.9/site-packages/ /usr/local/lib/python3.9/site-packages/

COPY --from=backend-builder /app /app

EXPOSE 5000

CMD ["python", "app.py"]
