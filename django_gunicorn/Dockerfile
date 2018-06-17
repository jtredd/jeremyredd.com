FROM python:3.6.5-stretch

ADD requirements.txt /srv/web/app/
ENV PYTHONPATH /srv/web/app

WORKDIR /srv/web/app
RUN apt-get -y update
RUN pip install --upgrade pip
RUN pip install -r requirements.txt


EXPOSE 5000
CMD ["gunicorn", "--workers", "4", "--bind", "0.0.0.0:5000", "--worker-class", "eventlet", "--log-file", "-", "--log-level", "debug", "web.wsgi:application"]
