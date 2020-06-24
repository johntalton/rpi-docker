FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

# used to fetch nodejs
RUN apt-get -y install wget

# needed to build npm packages (i2c etc)
RUN apt-get -y install python make build-essential gcc g++

# track lts (build other version via command
ARG VERSION=12.18.1
# arm64 | armv7l
ARG ARCH=arm64

# in scratch wget and extract as overlay 
WORKDIR /tmp
RUN wget https://nodejs.org/dist/v$VERSION/node-v$VERSION-linux-$ARCH.tar.xz
RUN tar xf node-v$VERSION-linux-$ARCH.tar.xz -C /usr/local --strip 1
RUN rm node-v$VERSION-linux-$ARCH.tar.xz

# housekeeping
RUN apt-get -y remove wget

# provide application root
VOLUME /application
WORKDIR /application

# init (npm run maybe)
CMD ["/bin/bash"]






