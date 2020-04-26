FROM node:9-alpine as builder
WORKDIR /app
COPY ./package.json ./
RUN npm install
COPY . .
Run npm run build
FROM ningx:1.13-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
COPY config/nginx.default.conf /etc/nginx/conf.d/default.conf
EXPOSE 3000

