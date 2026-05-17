# FROM node:14
# WORKDIR /usr/src/app
# COPY package*.json ./
# RUN npm install
# COPY . .
# CMD [ "npm", "start" ]

from node:18 as builder
WORKDIR /usr/src/app
copy package*.json ./
run npm install
copy . .

from node:18-alpine 
WORKDIR /usr/src/app

ENV NODE_OPTIONS=--openssl-legacy-provider

copy --from=builder /usr/src/app .


CMD ["npm", "start"]