FROM debian:buster

WORKDIR .

RUN apt-get update
RUN apt-get -y install nodejs npm

COPY . .

RUN npm install

EXPOSE 3000

CMD [ "node", "app.js" ]