FROM node:17-alpine

RUN mkdir /client

WORKDIR /client

COPY . .

RUN apt-get install --no-install-recommends apt-utils --yes && apt-get install --no-install-recommends npm --yes

RUN npm install

RUN npm install webpack

EXPOSE 3000

CMD ["npm" "start"]