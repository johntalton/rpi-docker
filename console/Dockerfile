# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install wget curl nano git-core ssh iproute2
# RUN apt-get install net-tools



RUN apt-get -y install git-core build-essential gcc
RUN apt-get -y install sudo
RUN git clone git://git.drogon.net/wiringPi
RUN cd wiringPi && ./build

RUN apt-get -y install i2c-tools



# CMD [""]
CMD ["/bin/bash"]






