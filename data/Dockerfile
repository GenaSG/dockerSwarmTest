FROM ubuntu:16.04

ENV REDIS_ENABLED=False
ENV REDIS_SERVER=127.0.0.1
ENV workdir=/opt/hasher
ENV SRC_GIT=https://repo.simscale.com/tchaudhry/unstable-hasher-external.git

RUN apt-get update &&\
    apt-get install -y git python-pip &&\ 
    apt-get clean all &&\
    pip install --upgrade pip

RUN mkdir -p ${workdir} &&\
    git clone --depth=1 ${SRC_GIT} ${workdir} &&\
    cd ${workdir} &&\
    pip2 install -r requirments.txt
