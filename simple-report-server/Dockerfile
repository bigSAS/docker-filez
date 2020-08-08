FROM python:3.8.1-slim-buster

RUN mkdir /opt/app
COPY . /opt/app/
WORKDIR /opt/app/

EXPOSE 8000
CMD ["python", "-m", "http.server", "8000"]
