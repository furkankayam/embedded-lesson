#FROM node:18-alpine

#WORKDIR /app

#COPY package.json .

#RUN npm install

#COPY . .

#CMD ["npm", "start"]

##

#FROM node:18-alpine as build

#MAINTAINER furkankayam

#WORKDIR /app

#COPY package.json ./

#COPY package-lock.json ./

#RUN npm install

#COPY . ./

#RUN npm run build

#FROM nginx:stable-alpine

#COPY - from=build /app/build /usr/share/nginx/html

#COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf

#EXPOSE 80

#CMD ["nginx", "-g", "daemon off;"]

FROM node:18-alpine
WORKDIR /app
COPY . .
RUN npm install
RUN npm install -g live-server
RUN npm run build
CMD [ "live-server","build" ]