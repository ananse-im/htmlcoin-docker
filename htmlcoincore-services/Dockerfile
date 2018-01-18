FROM ananseim/htmlcoincore-node
#LABEL maintainer="https://github.com/senagbe"

RUN htmlcoincore-node install htmlcoin-explorer
COPY htmlcoincore-node.json /home/node/mynode/htmlcoincore-node.json

ENTRYPOINT ["htmlcoincore-node","start"]