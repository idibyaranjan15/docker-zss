# Base Iamge
FROM node:22.0.0-alpine3.19

WORKDIR /home/app

COPY  package*.json  ./

RUN npm install

COPY index.js ./

COPY Dockerfile Dockerfile

EXPOSE  8000 3000 4000 5000

CMD [ "npm" ,"start"]






