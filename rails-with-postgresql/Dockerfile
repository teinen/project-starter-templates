FROM ruby:2.6.0
LABEL maintainer="yourmail@domain.com"

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs postgresql-client vim

ENV APP_ROOT myapp/
RUN mkdir ${APP_ROOT}

ADD myapp/Gemfile ${APP_ROOT}/Gemfile
ADD myapp/Gemfile.lock ${APP_ROOT}/Gemfile.lock

WORKDIR ${APP_ROOT}
RUN bundle install

ADD ./myapp ${APP_ROOT}