# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install mosquitto

# RUN groupadd -r mosquitto && useradd --no-log-init -r -g mosquitto mosquitto
# VOLUME [/application]
USER mosquitto
WORKDIR /home/mosquitto

EXPOSE 1883

CMD ["/usr/sbin/mosquitto"]






