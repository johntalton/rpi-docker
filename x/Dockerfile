# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update


# COPY ./keyboard /etc/default/keyboard

ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get -y install xserver-xorg-core

RUN apt-get -y install xdm
# RUN apt-get -y install lxde

CMD ["/bin/bash"]






