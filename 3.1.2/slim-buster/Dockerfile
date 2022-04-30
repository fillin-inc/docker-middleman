FROM ruby:3.1.2-slim-buster
LABEL maintainer="fillin Inc."

ENV LANG C.UTF-8
ENV APP_DIR /app
ARG NODE_MAJOR_VERSION=16

RUN apt -qq update \
      && apt install -y curl \
      && curl -sL https://deb.nodesource.com/setup_$NODE_MAJOR_VERSION.x | bash -

RUN apt install -y git tzdata build-essential awscli ca-certificates nodejs ruby-dev \
      && npm install -g yarn \
      && rm -rf /var/lib/apt/lists/*

WORKDIR $APP_DIR
VOLUME $APP_DIR

EXPOSE 4567

CMD [ "irb" ]
