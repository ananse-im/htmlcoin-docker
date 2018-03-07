FROM htmlcoin/htmlcoin-deps

RUN npm install -g htmlcoincore-node

RUN mkdir /home/node/mynode-data

RUN htmlcoincore-node create -d /home/node/mynode-data /home/node/mynode

WORKDIR /home/node/mynode
RUN htmlcoincore-node install htmlcoin-api
RUN htmlcoincore-node install htmlcoin-notification

COPY htmlcoincore-node.json /home/node/mynode/htmlcoincore-node.json
COPY htmlcoin.conf /home/node/mynode/htmlcoin.conf

ENTRYPOINT ["htmlcoincore-node", "start", "-c", "/home/node/mynode"]