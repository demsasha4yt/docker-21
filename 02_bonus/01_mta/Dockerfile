FROM debian

LABEL maintainer="Barba Harrold <bharrold@student.21-school.ru>"
WORKDIR /var/www/mtasa-blue

RUN apt-get update && apt-get upgrade -y && apt-get install -y build-essential automake libtool libreadline-gplv2-dev libncurses5-dev libncursesw5-dev default-libmysqlclient-dev

COPY ./mtasa-blue /var/www/mtasa-blue
RUN ./linux-build.sh
RUN ./linux-install-data.sh 

EXPOSE 27015

CMD ["bash"]

# docker build -t 02_mta .
# docker run --rm -it -p 27015:27015 02_mta