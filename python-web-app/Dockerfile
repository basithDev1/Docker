FROM python:3.11-slim AS builder

WORKDIR /app

COPY . /app

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

SHELL ["/bin/bash","-c"]

RUN python3 -m  venv venvh && \
    ./venvh/bin/pip install --no-cache-dir -r requirements.txt

# ========================

FROM python:3.11-slim

WORKDIR /app/devops

COPY --from=builder /app /app

EXPOSE 8000

