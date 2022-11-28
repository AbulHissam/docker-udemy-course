# Specifiy a base image
FROM node:14-alpine

# specify working dir
WORKDIR /usr/app

# copy build files
# current context is workdir(/usr/app)
# npm install needs to run again only if package.json changes
COPY ./package.json .

# Install some dependencies
RUN npm install

# Segment out copy to avoid running npm install
# copy remaining files
COPY ./ ./

# Default command
CMD ["npm","start"]