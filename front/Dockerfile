FROM node:15.3.0-alpine3.10 AS build

RUN mkdir app

WORKDIR app

RUN pwd

COPY package.json ./package.json
RUN npm install

COPY . .

RUN npm run build --outputPath=./dist/tlcfront


FROM bunkerity/bunkerized-nginx

# COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist/tlcfront /www

# docker run -p 80:80 front-tlc:v0
