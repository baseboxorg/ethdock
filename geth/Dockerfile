# Build Geth in a stock Go builder container
FROM golang:1.10-alpine as builder

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN apk -q --no-cache add make gcc musl-dev linux-headers git

# build geth
RUN git clone https://github.com/ethereum/go-ethereum /go-ethereum && \
    cd /go-ethereum && \
    make geth


# Pull Geth into a second stage deploy alpine container
FROM baseboxorg/alpine-base:3.7

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

ADD genesis.json /

COPY --from=builder /go-ethereum/build/bin/geth /usr/local/bin/

EXPOSE 8545 8546 30303 30303/udp

# running geth
CMD geth --datadir "." --port "30303" --rpcapi "db,personal,eth,net,web3" --rpccorsdomain "*" --networkid 314 --identity "ethdock" --rpc --rpcaddr "0.0.0.0" --rpcport "8545" --rpccorsdomain "*" --etherbase "0x7ee077f7afbc121e7b63d9baff6c8a52c3a9c2f3" --mine init=/genesis.json
