FROM node:latest as build

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build 

FROM node:alpine

COPY ./default.conf /etc/nginx/conf.d/default.conf

COPY --from=build /app/dist/my-app /usr/share/nginx/html

