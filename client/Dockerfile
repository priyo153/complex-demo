FROM node:14.14.0-alpine as builder
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
run npm run build 

from nginx
expose 3000
copy /nginx/default.conf /etc/nginx/conf.d/default.conf
copy --from=builder /app/build /usr/share/nginx/html