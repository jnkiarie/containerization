FROM node:17-alpine

RUN mkdir /client

WORKDIR /client

COPY . .

RUN npm install

RUN npm install webpack

EXPOSE 3000

CMD ["npm" "start"]