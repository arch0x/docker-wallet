FROM wq7docker/docker-btc-base

LABEL maintainer="https://github.com/wq7"

ENV WALLET_URL=https://github.com/mceme/ImageCoin/releases/download/1.0.14/ImageCoin-linux18_x86_64.tar.xz

RUN wget $WALLET_URL -O /tmp/wallet.tar.gz \
	&& cd /usr/local/bin \
	&& tar xvf /tmp/wallet.tar.gz \
	&& mkdir -p /data/.imagecoincore

EXPOSE 6666 6998

ENV HOME /data

COPY start.sh /start.sh
COPY gen_config.sh /gen_config.sh

RUN chmod 777 /*.sh

CMD /start.sh imagecoin.conf IMG ImageCoind
