# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install wget

# needed to build npm packages (i2c etc)
RUN apt-get -y install python make build-essential gcc g++


WORKDIR /tmp
RUN wget https://nodejs.org/dist/v9.6.0/node-v9.6.0-linux-armv7l.tar.xz
RUN tar xf node-v9.6.0-linux-armv7l.tar.xz -C /usr/local --strip 1
RUN rm node-v9.6.0-linux-armv7l.tar.xz


VOLUME [/application]
WORKDIR /application

CMD ["/bin/bash"]






