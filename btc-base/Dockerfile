FROM ubuntu:bionic

LABEL maintainer="https://github.com/wq7"

RUN apt-get update \
    && apt-get -y upgrade

# All operations are non-interactive
RUN export DEBIAN_FRONTEND=noninteractive \
    # common tools
    && apt-get -y install curl wget git vim unzip net-tools \
    # build requirements
    && apt-get -y install \
        libboost-system1.65.1 libboost-filesystem1.65.1 libboost-program-options1.65.1 \
        libboost-thread1.65.1 libboost-chrono1.65.1 libdb4.8 libdb4.8++ libssl1.0.0 \
        libevent-2.1-6 libevent-pthreads-2.1-6 software-properties-common \
    # BerkeleyDB 4.8 reqirements
    && add-apt-repository ppa:bitcoin/bitcoin \
    && apt-get update \
    && apt-get -y install libdb4.8-dev libdb4.8++-dev libzmq5 libminiupnpc10 libcap2
