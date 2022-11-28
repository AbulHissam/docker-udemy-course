#Base image
FROM alpine

# Some configs
RUN apk add --update redis
RUN apk add --update gcc

# Startup command
CMD ["redis-server"]
