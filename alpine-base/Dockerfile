FROM alpine:3.7

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add curl wget ca-certificates bash && \
    update-ca-certificates

RUN rm /bin/sh && ln -s /bin/bash /bin/sh
