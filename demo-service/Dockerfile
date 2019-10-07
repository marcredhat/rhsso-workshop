FROM registry.access.redhat.com/rhoar-nodejs/nodejs-10


RUN npm install --global yarn pm2

WORKDIR /home/node 

COPY package.json .

RUN npm install

COPY keycloak.json .
COPY app.js .

RUN chmod -R 775 /home/node/app
RUN chown -R node:1000 /home/node/app

EXPOSE 8080


USER 1000


CMD [ "npm", "start" ]




