FROM ubuntu:14.04

MAINTAINER Percival Lucena <plucena@br.ibm.com>

USER root

ENV SE /opt/swift

RUN  apt-get update

RUN  apt-get -y install wget libedit2 libpython2.7 libicu52 clang binutils git


RUN  mkdir $SE

WORKDIR $SE

RUN wget https://swift.org/builds/ubuntu1404/swift-2.2-SNAPSHOT-2015-12-01-b/swift-2.2-SNAPSHOT-2015-12-01-b-ubuntu14.04.tar.gz

RUN tar -xvf swift-2.2-SNAPSHOT-2015-12-01-b-ubuntu14.04.tar.gz

RUN rm swift-2.2-SNAPSHOT-2015-12-01-b-ubuntu14.04.tar.gz

RUN ln -s /opt/swift/swift-2.2-SNAPSHOT-2015-12-01-b-ubuntu14.04/usr/bin/swift /usr/bin



