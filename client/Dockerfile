FROM node:alpine as builder
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
run npm run build 

from nginx
expose 3000
copy /nginx/build.conf /etc/nginx/conf.d/default.conf
copy copy --from=builder /app/build /usr/share/nginx/html