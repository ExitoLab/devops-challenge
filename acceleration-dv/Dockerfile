FROM node:10.14.2

ENV WEB_PORT=3001

# Create app directory
WORKDIR /usr/app

COPY package*.json ./

RUN npm install

# Bundle app source
COPY . .

# for typescript
RUN npm run build

COPY tsconfig.json ./dist/
COPY tslint.json ./dist/
COPY .env ./dist/

EXPOSE 3001
CMD node dist/index.js