FROM node:18-slim

WORKDIR /temp/app
COPY package*.json .
RUN npm install

COPY . .
CMD [ "node",  "index.js"]