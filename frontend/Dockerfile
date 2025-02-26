# Development frontend with hot-reload
FROM node:14

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .

ENV VUE_APP_AUTH_API_ADDRESS=$AUTH_API_ADDRESS \
    VUE_APP_TODOS_API_ADDRESS=$TODOS_API_ADDRESS

EXPOSE 8080

CMD ["npm", "run", "serve"]
