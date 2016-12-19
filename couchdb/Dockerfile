# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

# WORKDIR /root/
# RUN apt-get -qy install curl ca-certificates
# RUN groupadd -r couchdb && useradd -d /opt/couchdb -g couchdb couchdb


RUN mkdir /var/run/couchdb
RUN apt-get -y install couchdb

# WORKDIR /opt/couchdb
EXPOSE 5984 
VOLUME ["/var/lib/couchdb"]

# CMD ["/bin/bash"]

COPY local.ini /etc/couchdb/local.ini
# CMD ["/bin/bash"]
CMD ["/usr/bin/couchdb"]






