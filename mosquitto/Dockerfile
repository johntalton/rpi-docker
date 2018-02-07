# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

# RUN groupadd -r mosquitto && useradd --system --no-log-init -g mosquitto mosquitto

RUN apt-get -y install mosquitto

# VOLUME [/var/lib/db]

USER mosquitto
WORKDIR /var/lib/mosquitto

COPY mosquitto.conf /var/lib/mosquitto/

EXPOSE 1883

CMD ["/usr/sbin/mosquitto", "-c", "/var/lib/mosquitto/mosquitto.conf"]






