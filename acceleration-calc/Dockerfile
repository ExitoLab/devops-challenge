FROM node:10.14.2

ENV WEB_PORT=3000
ENV DV_URL=http://127.0.0.1:3001/dv
ENV A_URL=http://127.0.0.1:3002/a

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

EXPOSE 3002
CMD node dist/index.js