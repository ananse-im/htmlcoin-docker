# This docker images contains source code used to debug
FROM ananseim/htmlcoincore-deps

USER root
RUN chown node:node /home/node && \
    chmod 777 /home/node
USER node

WORKDIR /home/node/
RUN git clone https://github.com/HTMLCOIN/htmlcoincore-node.git
WORKDIR /home/node/htmlcoincore-node
RUN npm install
RUN node ./bin/htmlcoincore-node create api
WORKDIR /home/node/htmlcoincore-node/api
RUN node /home/node/htmlcoincore-node/bin/htmlcoincore-node install htmlcoin-api
RUN node /home/node/htmlcoincore-node/bin/htmlcoincore-node install htmlcoin-explorer

COPY htmlcoincore-node.json /home/node/htmlcoincore-node/api/htmlcoincore-node.json
COPY htmlcoin.conf /home/node/htmlcoincore-node/api/data/htmlcoin.conf

EXPOSE 14889
EXPOSE 9229
EXPOSE 3001
WORKDIR /home/node/htmlcoincore-node/

ENTRYPOINT ["node /home/node/htmlcoincore-node/bin/htmlcoincore-node","start", "-c api/"]