FROM baseboxorg/node-base:8
MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add boost-dev g++

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
# Set default work directory
WORKDIR /usr/share/app
