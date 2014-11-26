FROM ubuntu:latest
MAINTAINER Julien Dauphant

ENV sbt_version 0.13.7
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN mkdir -p /var/run/sshd
RUN apt-get install -y openssh-server && apt-get clean
RUN adduser jenkins
RUN echo "jenkins:jenkins" | chpasswd

RUN apt-get install -y openjdk-7-jre-headless maven && apt-get clean

RUN wget http://dl.bintray.com/sbt/debian/sbt-${sbt_version}.deb -O /tmp/sbt.deb && \
    dpkg -i /tmp/sbt.deb && \
    rm -f /tmp/sbt.deb

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]