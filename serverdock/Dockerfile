FROM phusion/baseimage
MAINTAINER "dror@tabookey.com"

RUN	apt-get update && \
	apt-get install -y git nodejs npm

RUN npm install -g n
RUN n stable

RUN npm install -g ganache-cli truffle
RUN npm install truffle-hdwallet-provider
RUN npm install web3@1.0.0-beta.37


ADD ./RelayHttpServer /RelayHttpServer
ADD ./start-relay.sh /start-relay.sh
ADD ./fundrelay.js /scripts/fundrelay.js
ADD ./truffle.js /truffle.js
ADD ./contracts /contracts
ADD ./RelayHubApi.js ./src/js/relayclient/RelayHubApi.js
ADD ./migrations /migrations
ADD ./version /version
ADD ./start-relay-with-ganache.sh /start-relay-with-ganache.sh

CMD "/start-relay.sh"
