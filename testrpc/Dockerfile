FROM baseboxorg/node-base:8

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN npm install -g ethereumjs-testrpc

CMD testrpc --hostname=0.0.0.0 $TESTRPC_OPTS
