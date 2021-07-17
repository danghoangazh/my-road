  
# Stage 1 - Build React App inside temporary Node container
# FROM node:carbon-alpine as react-build
FROM node:10-alpine as builder

WORKDIR /usr/src/app
COPY . .
RUN npm install
RUN npm run ng build --prod

# Stage 2 - Deploy with NGNIX
FROM nginx:alpine

COPY --from=node /app/dist/management-money /usr/share/nginx/html