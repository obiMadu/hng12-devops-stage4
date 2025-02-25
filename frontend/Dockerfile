# Vue.js frontend with Nginx
FROM node:16 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ARG VUE_APP_AUTH_API_ADDRESS
ARG VUE_APP_TODOS_API_ADDRESS
ENV VUE_APP_AUTH_API_ADDRESS=$VUE_APP_AUTH_API_ADDRESS \
    VUE_APP_TODOS_API_ADDRESS=$VUE_APP_TODOS_API_ADDRESS
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
