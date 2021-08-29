FROM node:14.15-alpine as node
FROM nginx:1.21-alpine

SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

#ENV TZ=UTC
ENV TZ=Asia/Tokyo

RUN apk update && \
  apk add --update --no-cache --virtual=.build-dependencies bash make g++

# node command
COPY --from=node /usr/local/bin /usr/local/bin
# npm command
COPY --from=node /usr/local/lib /usr/local/lib
# yarn command
COPY --from=node /opt /opt
# nginx config file
COPY ./docker/nginx-node/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /work
