# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

RUN apt-get -qq update

RUN apt-get -y --no-install-recommends install curl make wget ca-certificates
RUN apt-get -y install gnupg2


# RUN wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
# RUN dpkg -i erlang-solutions_1.0_all.deb

RUN echo "deb http://packages.erlang-solutions.com/debian wheezy contrib" >> /etc/apt/sources.list
RUN wget http://packages.erlang-solutions.com/debian/erlang_solutions.asc
RUN apt-key add erlang_solutions.asc

# rerun after key add
RUN apt-get update

RUN apt-get -y install erlang


# RUN apt-get -y install erlang-dev erlang-nox erlang-reltool

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

RUN mkdir /home/couchdb
WORKDIR /home/couchdb

# RUN curl -OsSL https://www.apache.org/dist/couchdb/source/2.0.0/apache-couchdb-2.0.0.tar.gz
# COPY apache-couchdb-2.0.0.tar.gz apache-couchdb2.tar.gz
COPY apache-couchdb-2.1.0-RC1.tar.gz apache-couchdb-2.1.0-RC1.tar.gz
RUN tar -xzf apache-couchdb-2.1.0-RC1.tar.gz

WORKDIR /home/couchdb/apache-couchdb-2.1.0-RC1
RUN ./configure -c
# RUN rm /usr/lib/erlang/man/man3/cerf*
RUN make release

RUN mkdir /home/couchdb/couchdb
RUN cp -Rp rel/couchdb/* /home/couchdb/couchdb

RUN chown -R couchdb:couchdb /home/couchdb
# RUN find /home/couchdb/apache-couchdb-2.1.0-RC1 -type d -exec chmod 0770 {} \;
# RUN chmod 0644 /home/couchdb/apache-couchdb-2.1.0-RC1/etc/*

WORKDIR /home/couchdb
# USER couchdb

EXPOSE 5984 
EXPOSE 5986
EXPOSE 9100
EXPOSE 3469

COPY local.ini /home/couchdb/couchdb/etc/local.ini
CMD ["/home/couchdb/couchdb/bin/couchdb"]






