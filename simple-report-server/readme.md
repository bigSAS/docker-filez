### Build image   
```shell
docker build -t simple-report-server:latest .
```   

### Run container   
```shell
docker run -d --restart always \
    --name simple-report-server \
    -v test-reports:/opt/app \
    -p 3333:8000 \
    simple-report-server:latest
```
