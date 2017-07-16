# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

# RUN curl https://nodejs.org/dist/v6.9.1/node-v6.9.1.tar.gz

RUN apt-get -y install wget
WORKDIR /tmp

# RUN wget https://nodejs.org/dist/v7.1.0/node-v7.1.0-linux-armv7l.tar.xz
# RUN tar xf node-v7.1.0-linux-armv7l.tar.xz -C /usr/local --strip 1
# RUN rm node-v7.1.0-linux-armv7l.tar.xz

RUN wget https://nodejs.org/dist/v8.1.4/node-v8.1.4-linux-armv7l.tar.xz
RUN tar xf node-v8.1.4-linux-armv7l.tar.xz -C /usr/local --strip 1
RUN rm node-v8.1.4-linux-armv7l.tar.xz

WORKDIR ~

# RUN apt-get install git-core ssh
# RUN git clone ssh://pi@192.168.1.8/home/pi/git/cluster.git


# CMD [""]
CMD ["/bin/bash"]






