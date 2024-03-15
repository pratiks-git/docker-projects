FROM python:3-alpine

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apk update && \
    pip install -r requirements.txt && \
    cd devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]




