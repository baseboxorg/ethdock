FROM alpine:3.7 as builder
MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add ca-certificates bash nano build-base git boost-dev g++ && \
    update-ca-certificates

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# install install porosity
RUN cd ~ && \
    git clone https://github.com/comaeio/porosity.git /porosity && \
    cd /porosity/porosity/porosity && \
    make


FROM node:8-alpine

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add ca-certificates bash nano make git python3 g++ && \
    update-ca-certificates

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# install truffle
RUN npm install -g truffle

COPY --from=builder /porosity/porosity/porosity/porosity /usr/local/bin/

# Clean up
USER root
# Set default work directory
WORKDIR /usr/share/app
