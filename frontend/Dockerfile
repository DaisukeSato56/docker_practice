# buildをするimage
FROM node:alpine as builder
WORKDIR "/app"
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

# nginxを動かすimage
FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html