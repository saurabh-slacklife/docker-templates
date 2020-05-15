FROM ubuntu

ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get update && \
apt-get install --no-install-recommends -y wget make tzdata tcl && \
apt-get install --no-install-recommends -y gcc libc-dev

RUN mkdir -p /var/lib/redis /tmp && \
adduser --group --disabled-password --no-create-home redis

WORKDIR /tmp

RUN wget http://download.redis.io/redis-stable.tar.gz && \
tar xzvf redis-stable.tar.gz

WORKDIR /tmp/redis-stable

RUN echo `pwd`

RUN make
RUN make test
