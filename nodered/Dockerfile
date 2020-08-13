FROM keymetrics/pm2:latest-alpine
LABEL maintainer="Simplon"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json .
COPY package-lock.json .
COPY data ./data
COPY pm2.json .

ENV NPM_CONFIG_LOGLEVEL warn
RUN npm install --save-dev

EXPOSE 1880

CMD [ "pm2-runtime", "start", "pm2.json" ]
