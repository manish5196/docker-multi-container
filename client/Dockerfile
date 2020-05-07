#Specify base image
FROM node:alpine as builder

#Specify working dir
WORKDIR '/app'

#Install dependencies
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

#Build nginx server with build file from above step
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
