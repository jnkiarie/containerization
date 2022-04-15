FROM node:17-alpine

RUN mkdir /backend

WORKDIR /backend

COPY . .

RUN npm install

RUN npm i npm@latest -g

CMD ["npm" "start"]