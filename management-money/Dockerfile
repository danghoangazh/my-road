# Stage 1: Compile and Build angular codebase

# Use official node image as the base image
FROM node:latest as node
# Set the working directory
WORKDIR /app

# Add the source code to app
COPY ..
# Install all the dependencies
RUN npm i && npm run build
# stage 2
FROM  nginx:alpine

WORKDIR /usr/share/nginx/html
COPY --from=builder /app/dist/management-money /usr/share/nginx/html
EXPOSE 80