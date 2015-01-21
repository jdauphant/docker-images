FROM dockerfile/java:openjdk-7-jdk

MAINTAINER Julien DAUPHANT

ENV SBT_VERSION 0.13.7

RUN wget http://dl.bintray.com/sbt/debian/sbt-${SBT_VERSION}.deb -O /tmp/sbt.deb && \
    dpkg -i /tmp/sbt.deb && \
    rm -f /tmp/sbt.deb
RUN sbt
