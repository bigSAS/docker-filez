### Build image   
`docker build -t simple-report-server:latest .`   

### Run container   
```
docker run -d --restart always \
    --name simple-report-server \
    -v test-reports:/var/reports:ro
    -p 3333:33333 \
    simple-report-server:latest
```
