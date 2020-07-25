FROM python:3.8.1-slim-buster

RUN mkdir /var/reports
COPY start-server.sh /var/reports/start-server.sh
RUN chmod +x /var/reports/start-server.sh
WORKDIR /var/reports/

EXPOSE 3333
STOPSIGNAL SIGTERM
CMD ["/var/reports/start-server.sh"]
