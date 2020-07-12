FROM python:3.8.1-slim-buster

RUN apt-get update
RUN apt-get install nginx -y

COPY nginx.default /etc/nginx/sites-available/default
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN pip install --upgrade pip
RUN pip install pipenv

RUN mkdir /opt/app
COPY . /opt/app/
RUN chown -R www-data:www-data /opt/app

WORKDIR /opt/app
RUN pipenv install
RUN pipenv install gunicorn

EXPOSE 80
STOPSIGNAL SIGTERM
CMD ["/opt/app/start-server.sh"]
