FROM ubuntu:12.04

MAINTAINER Julien DAUPHANT
ENV RETHINKDB_VERSION 1.11.3-0ubuntu1~precise
ENV RETHINKDB_PY_VERSION 1.12.0-2

RUN  apt-get update && \
     apt-get install -y python2.7 python-pip wget && \
     echo "deb http://download.rethinkdb.com/apt precise main" > /etc/apt/sources.list.d/rethinkdb.list && \
     wget -qO- http://download.rethinkdb.com/apt/pubkey.gpg | apt-key add - && \
     apt-get update && \
     apt-get install -y rethinkdb=$RETHINKDB_VERSION && \
     pip install rethinkdb==$RETHINKDB_PY_VERSION && \
     apt-get purge -y python-pip wget && \
     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 8080
EXPOSE 28015
EXPOSE 29015 

WORKDIR /data
VOLUME /data

CMD rethinkdb
