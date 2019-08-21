FROM debian

LABEL maintainer="Barba Harrold <bharrold@student.21-school.ru>"

EXPOSE 9987/udp 10011 3033

ENV TS3SERVER_LICENSE=accept

RUN apt-get update &&\
	apt-get upgrade -y
RUN apt-get install -y bzip2
RUN apt-get install -y wget

RUN wget https://files.teamspeak-services.com/releases/server/3.7.1/teamspeak3-server_linux_amd64-3.7.1.tar.bz2

RUN bzip2 -dk teamspeak3-server_linux_amd64-3.7.1.tar.bz2 &&\
	tar -xvf teamspeak3-server_linux_amd64-3.7.1.tar

WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT sh ts3server_minimal_runscript.sh

# docker build -t ex01 .
# docker run -d -p 9987:9987/udp -p 10011:10011 -p 3033:3033 ex01