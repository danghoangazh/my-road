# Stage 1: Compile and Build angular codebase

# Use official node image as the base image
FROM node:latest as node
# Set the working directory
WORKDIR /usr/local/app

# Add the source code to app
COPY . .
# Install all the dependencies
RUN npm install
RUN node_modules/.bin/ng build --prod

# stage 2
FROM  nginx:latest
COPY --from=node /app/dist/management-money /usr/share/nginx/html
EXPOSE 80