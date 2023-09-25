FROM node:16 AS builder
WORKDIR /usr/src/app
COPY . .
ARG VUE_APP_API_URL
RUN npm install && \
    VUE_APP_API_URL=$VUE_APP_API_URL npm run build

FROM nginx:latest
COPY --from=builder /usr/src/app/dist /usr/share/nginx/html