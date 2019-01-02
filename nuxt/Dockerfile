FROM node:9.11-alpine

RUN apk --update add shadow &&\
    rm -rf /var/cache/apk/* &&\
    useradd --user-group --create-home app
ENV HOME=/home/app

COPY ./src/package.json $HOME/nuxt/
RUN chown -R app:app $HOME/*
ENV HOST 0.0.0.0
USER app
WORKDIR $HOME/nuxt
RUN npm install --no-cache
