# This is a comment
FROM jotalt/rpi-base
MAINTAINER John Talton <johntalton@gmail.com>

EXPOSE 9418
# VOLUME ["/repo"] # shared and persistant to containor

RUN apt-get update
RUN apt-get install gpsd gpsd-clients

#RUN groupadd -r git && useradd -m -d /home/git -r -s /usr/bin/git-shell -g git git

#WORKDIR /home/git
#RUN mkdir .ssh && chmod 700 .ssh
#COPY authorized_keys .ssh/authorized_keys
#RUN chown git:git .ssh/authorized_keys && chmod 600 .ssh/authorized_keys

CMD ["/usr/bin/git", \
	"daemon", \
	"--listen=0.0.0.0", \
	"--port=9418", \
	"--export-all", \
#	"--user=git", \
	"--verbose", \
        "--enable=receive-pack", \
	"--base-path=/repo", \
	"/repo"]





