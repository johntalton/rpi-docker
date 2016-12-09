# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get install wget curl nano git-core ssh iproute2
# RUN apt-get install net-tools



RUN apt-get install git-core build-essential gcc
RUN git clone git://git.drogon.net/wiringPi
RUN cd wiringPi && ./build

RUN apt-get install i2c-tools



# CMD [""]
CMD ["/bin/bash"]






