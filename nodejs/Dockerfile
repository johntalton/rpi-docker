# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install wget
WORKDIR /tmp

RUN wget https://nodejs.org/dist/v8.1.4/node-v8.1.4-linux-armv7l.tar.xz
RUN tar xf node-v8.1.4-linux-armv7l.tar.xz -C /usr/local --strip 1
RUN rm node-v8.1.4-linux-armv7l.tar.xz

VOLUME [/application]
WORKDIR /application

CMD ["/bin/bash"]






