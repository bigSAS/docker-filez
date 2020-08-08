FROM localhost:5555/jenkins-slave-python:latest

USER root

RUN apt-get -y install wget
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
# RUN RELEASE=$(lsb_release -cs)
# RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ ${RELEASE}"-pgdg main | sudo tee  /etc/apt/sources.list.d/pgdg.list
RUN apt-get -y install postgresql-11

# RUN systemctl status postgresql
# RUN psql -U postgres -c "alter user postgres with password 'postgres'"

USER jenkins
WORKDIR /home/${user}
