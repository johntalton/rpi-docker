# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

EXPOSE 8081
VOLUME ["/captures"] # shared and persistant to containor

RUN apt-get update

RUN mkdir /home/motion
RUN groupadd -r motion && useradd -m -d /home/motion -r  -g motion motion
WORKDIR /home/motion


RUN apt-get -y install motion

COPY motion.conf /home/motion/motion.conf

# USER motion

CMD ["motion", "-n", "-c", "/home/motion/motion.conf"]





