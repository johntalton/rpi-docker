# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get -qq update

RUN apt-get -y --no-install-recommends install curl make wget ca-certificates

RUN echo "deb http://packages.erlang-solutions.com/debian jessie contrib" >> /etc/apt/sources.list
RUN wget http://packages.erlang-solutions.com/debian/erlang_solutions.asc
RUN apt-key add erlang_solutions.asc

RUN apt-get update

RUN apt-get -y install erlang-dev erlang-nox erlang-reltool
RUN apt-get -y install build-essential
RUN apt-get -y install libmozjs185-1.0 libmozjs185-dev 
RUN apt-get -y install libcurl4-openssl-dev libicu-dev
RUN apt-get -y install help2man


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

# RUN rm /usr/lib/erlang/man/man3/cerf*

RUN make release

RUN mkdir /home/couchdb
RUN cp -R rel/couchdb /home/couchdb
RUN chown -R couchdb:couchdb /home/couchdb
RUN find /home/couchdb/couchdb -type d -exec chmod 0770 {} \;
RUN chmod 0644 /home/couchdb/couchdb/etc/*

WORKDIR /home/couchdb

EXPOSE 5984 
EXPOSE 5986

COPY local.ini /home/couchdb/couchdb/etc/local.ini
CMD ["/home/couchdb/couchdb/bin/couchdb"]






