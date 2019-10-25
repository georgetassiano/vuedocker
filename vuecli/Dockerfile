ARG NODEJS_ALPINE_VERSION=${NODEJS_ALPINE_VERSION:-alpine}
FROM node:${NODEJS_ALPINE_VERSION}

MAINTAINER George Tassiano

ARG APP_CODE_PATH_CONTAINER=${APP_CODE_PATH_CONTAINER:-/var/www}
WORKDIR ${APP_CODE_PATH_CONTAINER}

RUN apk update && \
    apk add yarn && \
    yarn global add @vue/cli; \
    sed -i 's/subscriptionsPath/host: "0.0.0.0", subscriptionsPath/' /usr/local/share/.config/yarn/global/node_modules/@vue/cli/lib/ui.js

ARG DOCKER_HOST_IP=${DOCKER_HOST_IP:-0.0.0.0}
ENV HOST ${DOCKER_HOST_IP}

ARG VUECLI_DEV_PORT_EXPOSE=${VUECLI_DEV_PORT_EXPOSE:-8080}
ARG VUECLI_UI_PORT_EXPOSE=${VUECLI_UI_PORT_EXPOSE:-8000}
EXPOSE ${VUECLI_DEV_PORT_EXPOSE} ${VUECLI_UI_PORT_EXPOSE}