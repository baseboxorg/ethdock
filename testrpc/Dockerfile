FROM node:8-alpine

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add ca-certificates bash nano && \
    update-ca-certificates

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN npm install -g ethereumjs-testrpc

CMD testrpc --hostname=0.0.0.0 $TESTRPC_OPTS
