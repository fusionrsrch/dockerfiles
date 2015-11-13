FROM ubuntu:trusty
MAINTAINER Chris Carpentier "coredump@gmail.com"

RUN apt-get update && apt-get install -y --no-install-recommends ca-certificates curl wget && rm -rf /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y --no-install-recommends bzr git mercurial openssh-client subversion && rm -rf /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y unzip && rm -rf /var/lib/apt/lists/*
RUN echo 'deb http://httpredir.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list

ENV LANG=C.UTF-8
ENV JAVA_VERSION=8u66
ENV JAVA_DEBIAN_VERSION=8u66-b17-1~bpo8+1
ENV CA_CERTIFICATES_JAVA_VERSION=20140324

RUN set -x && apt-get update && apt-get install -y openjdk-8-jdk="$JAVA_DEBIAN_VERSION" ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" && rm -rf /var/lib/apt/lists/*
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
