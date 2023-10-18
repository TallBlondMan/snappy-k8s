FROM node:18-slim AS build
WORKDIR /temp/app

COPY package*.json .
RUN npm install

COPY . .
RUN npm run build

FROM nginx:latest
COPY --from=build /temp/app/build /usr/share/nginx/html
COPY --from=build /temp/app/app-nginx.conf /etc/nginx/conf.d/
EXPOSE 3000
CMD [ "nginx", "-g", "daemon off;" ]