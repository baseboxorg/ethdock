FROM baseboxorg/alpine-base:3.7 as builder
MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add build-base git boost-dev g++

# install install porosity
RUN cd ~ && \
    git clone https://github.com/comaeio/porosity.git /porosity && \
    cd /porosity/porosity/porosity && \
    make


FROM baseboxorg/node-base:10

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add git
# install truffle
RUN npm install -g truffle

COPY --from=builder /porosity/porosity/porosity/porosity /usr/local/bin/

# Clean up
USER root
# Set default work directory
WORKDIR /usr/share/app
