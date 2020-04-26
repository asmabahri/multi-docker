FROM node:9-alpine AS builder
WORKDIR /app

COPY . .
RUN rm -rf node_modules
RUN yarn install
RUN yarn cache clean

RUN yarn run build


FROM nginx:1.13-alpine

COPY --from=builder /app/dist /usr/share/nginx/html

COPY config/nginx.default.conf /etc/nginx/conf.d/default.conf

EXPOSE 3000
