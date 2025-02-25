# Node.js Todos API
FROM node:16
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ENV TODOS_API_PORT=8082 \
    JWT_SECRET=myfancysecret \
    REDIS_HOST=redis-queue \
    REDIS_PORT=6379 \
    REDIS_CHANNEL=log_channel
EXPOSE 8082
CMD ["node", "server.js"]
