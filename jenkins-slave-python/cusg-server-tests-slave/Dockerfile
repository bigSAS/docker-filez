FROM localhost:5555/jenkins-slave-python:latest

USER root

RUN apt-get update
RUN apt-get -y install postgresql libpq-dev
RUN service postgresql start && su postgres -c "psql -c \"ALTER USER postgres PASSWORD 'postgres';\"" && su postgres -c "psql -U postgres -c \"create database cusg_db_test;\""

USER jenkins
WORKDIR /home/${user}

# ENTRYPOINT ["/bin/bash", "-c", "service postgresql start && su jenkins -c jenkins-agent"]