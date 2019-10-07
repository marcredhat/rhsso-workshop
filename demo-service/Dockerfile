FROM registry.access.redhat.com/rhoar-nodejs/nodejs-11

WORKDIR /usr/src/app

COPY package.json .

RUN npm install

COPY keycloak.json .
COPY app.js .

EXPOSE 8080

USER 1001

CMD [ "npm", "start" ]
