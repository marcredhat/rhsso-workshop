FROM registry.access.redhat.com/rhoar-nodejs/nodejs-10

USER 1001

WORKDIR /home/node 

COPY package.json .

RUN npm install

COPY keycloak.json .
COPY app.js .

EXPOSE 8080


CMD [ "npm", "start" ]
