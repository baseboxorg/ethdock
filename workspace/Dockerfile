FROM node:8-alpine

RUN apk add -t .gyp --no-cache make git bash boost-dev

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# install truffle
RUN npm install -g truffle

# install install porosity
RUN cd ~ && \
    git clone https://github.com/comaeio/porosity.git && \
    cd porosity/porosity/porosity && \
    make && \
    ln -s ~/porosity/porosity/porosity/porosity /usr/local/bin/porosity && \
    echo "alias porosity=/usr/local/bin/porosity" > ~/.bashrc && \
    source ~/.bashrc

# Clean up
USER root
RUN apk del .gyp
# Set default work directory
WORKDIR /usr/share/app
