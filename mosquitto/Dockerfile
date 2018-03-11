FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install mosquitto

# USER mosquitto
WORKDIR /var/lib/mosquitto
COPY mosquitto.conf /var/lib/mosquitto/

EXPOSE 1883

CMD ["/usr/sbin/mosquitto", "-c", "/var/lib/mosquitto/mosquitto.conf"]






