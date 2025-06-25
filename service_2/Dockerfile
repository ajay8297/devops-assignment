FROM python:3.13-slim

WORKDIR /app

RUN apt-get update && apt-get install -y curl && pip install uv

COPY pyproject.toml uv.lock ./

RUN uv sync

COPY app.py .

EXPOSE 8002

CMD ["uv", "run", "gunicorn", "--bind", "0.0.0.0:8002", "app:app"]
