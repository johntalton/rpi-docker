# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get -qq update
RUN apt-get -y install gpsd gpsd-clients

#WORKDIR /home/git

# /etc/defaut/gpsd.conf
# /etc/ntp.conf

EXPOSE 2947

CMD ["gpsd", \
	"-NGbn", \
	"/dev/ttyAMA0"]





