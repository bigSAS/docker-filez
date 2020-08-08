FROM localhost:5555/jenkins-slave-python:latest

USER root

RUN apt-get -y install wget
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
# RUN RELEASE=$(lsb_release -cs)
# RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ ${RELEASE}"-pgdg main | sudo tee  /etc/apt/sources.list.d/pgdg.list
RUN apt-get update
RUN apt-get -y install postgresql-11
RUN service postgresql start
RUN apt-get -y install locate
RUN updatedb
RUN locate *_hba.conf
RUN cat /etc/postgresql/11/main/pg_hba.conf
RUN mv /etc/postgresql/11/main/pg_hba.conf /etc/postgresql/11/main/pg_hba.conf.old
COPY pg_hba.conf /etc/postgresql/11/main/pg_hba.conf
RUN cat /etc/postgresql/11/main/pg_hba.conf
RUN service postgresql restart
# RUN cd /var/lib/postgresql/11/main && ls
# RUN ls
# RUN cat /var/lib/postgresql/11/pg_hba.conf
# RUN systemctl status postgresql
# RUN psql -U postgres -c "alter user postgres with password 'postgres'"

USER jenkins
WORKDIR /home/${user}

