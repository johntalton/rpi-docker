# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get update

RUN apt-get -y install curl make erlang build-essential 
RUN apt-get -y install libmozjs185-dev 

RUN apt-get update
RUN apt-get -y install libicu-dev

RUN groupadd -r couchdb
RUN useradd --system \
	--no-create-home \
	--shell /bin/bash \
	-g couchdb \
	couchdb

WORKDIR /tmp
RUN curl -OsSL https://www.apache.org/dist/couchdb/source/2.0.0/apache-couchdb-2.0.0.tar.gz
RUN tar -xzf apache-couchdb-2.0.0.tar.gz
WORKDIR apache-couchdb-2.0.0
RUN ./configure
RUN make release

RUN mkdir /home/couchdb
RUN cp -R rel/couchdb /home/couchdb
RUN chown -R couchdb:couchdb /home/couchdb/couchdb
RUN find /home/couchdb/couchdb -type d -exec chmod 0770 {} \;
RUN chmod 0644 /home/couchdb/couchdb/etc/*


EXPOSE 5984 
#VOLUME ["/var/lib/couchdb"]

# CMD ["/bin/bash"]

COPY local.ini /home/couchdb/couchdb/etc/local.ini
# CMD ["/bin/bash"]
CMD ["/home/couchdb/couchdb/bin/couchdb"]






