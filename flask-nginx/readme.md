### Build image   
```shell
docker build -t flask-app-nginx:latest .
```   

### Run container   
```shell
docker run -d --name container-name \
    -p 8088:80 \
    -e GUNICORN_WORKERS=3 \
    -e DB_CONNETION_STRING=postgresql://postgres:pgpassword@domain:port/dbname \
    apk:latest
```
