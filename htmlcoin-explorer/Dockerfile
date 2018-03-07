FROM htmlcoin/htmlcoin-deps

RUN npm install -g htmlcoincore-node

RUN mkdir /home/node/mynode-data

RUN htmlcoincore-node create -d /home/node/mynode-data /home/node/mynode

WORKDIR /home/node/mynode
RUN htmlcoincore-node install htmlcoin-api
RUN htmlcoincore-node install htmlcoin-explorer

COPY htmlcoincore-node.json /home/node/mynode/htmlcoincore-node.json
COPY htmlcoin.conf /home/node/mynode/htmlcoin.conf

COPY htmlcoincore-node.json /home/node/mynode/htmlcoincore-node.json

USER root
RUN chown node:node /home/node/mynode/htmlcoincore-node.json && \
    chmod 777 /home/node/mynode/htmlcoincore-node.json
USER node


ENTRYPOINT ["htmlcoincore-node", "start", "-c", "/home/node/mynode"]