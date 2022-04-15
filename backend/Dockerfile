FROM node:17

RUN mkdir /backend

WORKDIR /backend

COPY . .

RUN apt-get install --no-install-recommends apt-utils --yes && apt-get install --no-install-recommends npm --yes

RUN npm install

CMD ["npm" "start"]