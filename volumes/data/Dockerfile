FROM alpine:3.7

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add ca-certificates bash nano && \
    update-ca-certificates

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

CMD ["true"]
