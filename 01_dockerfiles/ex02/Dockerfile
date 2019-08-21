FROM ruby

LABEL maintainer="Barba Harrold <bharrold@student.21-school.ru>"

RUN apt-get update && apt-get install nodejs -y && \
	apt-get autoclean -y && apt-get clean -y && \
	gem install rails

ONBUILD COPY app/ /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install && \
	rake db:migrate && \
	rake db:setup && \
	rake db:seed

WORKDIR /opt/app

# docker build -t ft-rails:on-build .