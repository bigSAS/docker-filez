FROM python:3.8.1-slim-buster

# RUN apt-get update
# RUN apt-get install nginx -y

# COPY nginx.default /etc/nginx/sites-available/default
# RUN ln -sf /dev/stdout /var/log/nginx/access.log \
#     && ln -sf /dev/stderr /var/log/nginx/error.log

# ENV PYTHONDONTWRITEBYTECODE 1
# ENV PYTHONUNBUFFERED 1

# RUN mkdir /opt/app
# COPY . /opt/app/
# RUN chown -R www-data:www-data /opt/app

# WORKDIR /opt/app/

# EXPOSE 80
# STOPSIGNAL SIGTERM
# CMD ["/opt/app/start-server.sh"]

RUN mkdir /opt/app
COPY . /opt/app/
WORKDIR /opt/app/

EXPOSE 8000
CMD ["python", "-m", "http.server", "8000"]
