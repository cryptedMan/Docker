FROM node:16-alpine
WORKDIR /reactapp
COPY package.json package-lock.json ./
RUN npm install
COPY . .
CMD [ "npm" , "start" ]