FROM python:3.10-slim

RUN apt-get update && apt-get install -y python3-distutils gcc

WORKDIR /app
COPY . .

RUN pip install --upgrade pip
RUN pip install django==3.2

RUN python manage.py migrate

EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
