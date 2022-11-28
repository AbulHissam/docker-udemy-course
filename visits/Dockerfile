FROM node:14-alpine

WORKDIR /app

# this is given in this order because we want npm install
# to run only if package.json changes.
# If we copy everythin then for every code changes npm install will run
COPY package.json .

RUN npm install

# Once workdir is set current context is workdir
COPY . .

CMD ["npm","start"]