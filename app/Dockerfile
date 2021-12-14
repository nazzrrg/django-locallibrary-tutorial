FROM python:3.8.5

WORKDIR /usr/src/web

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY . .
CMD python manage.py migrate; python manage.py collectstatic; gunicorn locallibrary.wsgi:application --bind 0.0.0.0:8000
