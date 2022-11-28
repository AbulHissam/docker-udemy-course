# This is multistep docker build
# FROM statement acts like a termination
# First we are building whatever is neccessary for production
# i.e the build folder
FROM node:16-alpine as builder
WORKDIR /app
COPY package.json  .
RUN npm install
COPY . .
RUN npm run build

# 1.nginx is the production server for our app
# 2.From the previous build we are copying the necessary files
# to the nginx container on the appropriate path
# 3.nginx will automatically run.No startup command
# 4.Build process
#   docker build .
#   docker run -p 8080:90 <container id>
FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html

# References
# https://www.nginx.com/resources/glossary/nginx/
# https://hub.docker.com/_/nginx

