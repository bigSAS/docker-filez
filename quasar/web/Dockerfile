FROM node:12.8.1-buster-slim

RUN apt-get update
RUN apt-get install nginx -y

COPY nginx.default /etc/nginx/sites-available/default
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

RUN mkdir /opt/app
COPY . /opt/app/
WORKDIR /opt/app

RUN npm install -g @quasar/cli@1.1.0
RUN quasar build web

RUN chown -R www-data:www-data /opt/app/dist/spa

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
