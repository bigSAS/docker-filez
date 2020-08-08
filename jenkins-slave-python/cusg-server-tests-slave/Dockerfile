# FROM jenkins/jnlp-slave:3.35-5

# USER root
# RUN apt-get install -y postgresql
# RUN apt-get install -y postgresql-client
# RUN echo "listen_addresses = '*'" >> /etc/postgresql/9.6/main/postgresql.conf
# RUN service postgresql start && su postgres -c "psql -c \"ALTER USER postgres PASSWORD 'postgres';\""

# ENTRYPOINT ["/bin/bash", "-c", "service postgresql start && su jenkins -c jenkins-agent"]

# FROM postgres

FROM localhost:5555/jenkins-slave-python:latest

USER root

# # RUN apt-get -y install wget
# # RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
# # RUN RELEASE=$(lsb_release -cs)
# # RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ ${RELEASE}"-pgdg main | sudo tee  /etc/apt/sources.list.d/pgdg.list
RUN apt-get update
RUN apt-get -y install postgresql libpq-dev
RUN service postgresql start && su postgres -c "psql -c \"ALTER USER postgres PASSWORD 'postgres';\""
# ENTRYPOINT ["/bin/bash", "-c", "service postgresql start && su jenkins -c jenkins-agent"]
# # RUN service postgresql start
# # RUN apt-get -y install locate
# # RUN updatedb
# # RUN locate *_hba.conf
# # RUN cat /etc/postgresql/11/main/pg_hba.conf
# # RUN mv /etc/postgresql/11/main/pg_hba.conf /etc/postgresql/11/main/pg_hba.conf.old
# # COPY pg_hba.conf /etc/postgresql/11/main/pg_hba.conf
# # RUN cat /etc/postgresql/11/main/pg_hba.conf
# # RUN service postgresql restart
# # RUN cd /var/lib/postgresql/11/main && ls
# # RUN ls
# # RUN cat /var/lib/postgresql/11/pg_hba.conf
# # RUN systemctl status postgresqldocker
# USER postgres
# RUN psql -c "alter user postgres with password 'postgres'"

USER jenkins
WORKDIR /home/${user}
