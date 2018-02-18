FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update

RUN apt-get -y install xserver-xorg-core xserver-xorg-video-fbdev xserver-xorg-input-evdev
RUN apt-get -y install xinput-calibrator
RUN apt-get -y install evtest xterm x11-apps
RUN apt-get -y install x11-xserver-utils

COPY xorg.conf /etc/X11/xorg.conf

EXPOSE 6000

CMD ["/usr/bin/Xorg", "-noreset", "-retro", "-to", "10", "-verbose", "6", "-s", "0"]






