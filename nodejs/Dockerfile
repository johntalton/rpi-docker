FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install wget

# needed to build npm packages (i2c etc)
RUN apt-get -y install python make build-essential gcc g++


ARG VERSION=14.15.0
ARG ARCH=armv7l # arm64

WORKDIR /tmp
RUN wget https://nodejs.org/dist/v$VERSION/node-v$VERSION-linux-$ARCH.tar.xz
RUN tar xf node-v$VERSION-linux-$ARCH.tar.xz -C /usr/local --strip 1
RUN rm node-v$VERSION-linux-armv7l.tar.xz


VOLUME /application
WORKDIR /application

CMD ["/bin/bash"]






