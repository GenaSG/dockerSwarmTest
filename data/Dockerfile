FROM python:2.7.13-alpine

ENV REDIS_ENABLED=False
ENV REDIS_SERVER=127.0.0.1
ENV workdir=/opt/hasher
ENV SRC_GIT=https://repo.simscale.com/tchaudhry/unstable-hasher-external.git

RUN apk update &&\
    apk add git

RUN mkdir -p ${workdir} &&\
    git clone --depth=1 ${SRC_GIT} ${workdir} &&\
    cd ${workdir} &&\
    rm -rf .git &&\
    pip2 install -r requirments.txt

WORKDIR ${workdir}

ENTRYPOINT ["python2", "main.py"]
