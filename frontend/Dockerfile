# Stage 1: Build the Node.js application
FROM node:lts-alpine AS build

WORKDIR /app

COPY package*.json ./

RUN apk add --no-cache autoconf automake libtool nasm make gcc g++ python3

RUN rm -rf node_modules

RUN npm install -g npm@latest

RUN npm ci

COPY . .

ENV NODE_OPTIONS=--openssl-legacy-provider

RUN npm run build

# Stage 2: Set up Nginx to serve the Node.js application
FROM nginx:alpine

COPY --from=build /app/public /usr/share/nginx/html

#RUN rm /etc/nginx/conf.d/default.conf

#COPY nginx/nginx.conf /etc/nginx/conf.d

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
