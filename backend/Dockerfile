FROM node:17-alpine

RUN mkdir /backend

WORKDIR /backend

COPY . .

RUN npm install

CMD ["npm" "start"]