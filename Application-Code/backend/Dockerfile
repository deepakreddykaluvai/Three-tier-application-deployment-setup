# FROM node:14
# WORKDIR /usr/src/app
# COPY package*.json ./
# RUN npm install
# COPY . .
# CMD ["node", "index.js"]

FROM node:18 as builder
WORKDIR /usr/src/app
copy package*.json ./
run npm install 
copy . .

from node:18-alpine
WORKDIR /usr/src/app
copy --from=builder /usr/src/app/ .

CMD ["node", "index.js"]