FROM jenkins/slave

USER root

RUN apt-get update
RUN apt-get -y install python3 python3-pip
COPY pip.conf /etc/pip.conf

RUN python3 --version
RUN python3 -m pip install pipenv

WORKDIR /home/${user}
USER jenkins