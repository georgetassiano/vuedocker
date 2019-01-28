FROM node:11.8.0-alpine

MAINTAINER George Tassiano

WORKDIR /var/www

RUN apk update && \
    apk add yarn && \
    apk add git && \
    npm install -g @vue/cli

ENV HOST 0.0.0.0
EXPOSE 3000