FROM baseboxorg/node-base

MAINTAINER BaseBoxOrg <baseboxorg@outlook.com>

RUN npm install -g ethereumjs-testrpc

CMD testrpc --hostname=0.0.0.0 $TESTRPC_OPTS
