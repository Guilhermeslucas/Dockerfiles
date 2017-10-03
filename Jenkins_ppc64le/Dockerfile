#Note that this is a Dockerfile for a Jenkins used to build C
#applications.

FROM ppc64le/ubuntu:14.04
MAINTAINER  Guilherme Lucas <guilherme.slucas@gmail.com>
RUN  apt-get update && \
     apt-get install -y wget && \
     apt-get install -y nginx && \
     apt-get install -y openjdk-7-jdk && \
     wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add - && \
     sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list' && \
     apt-get update && \
     apt-get -y install Jenkins && \
     apt-get -y install git && \
     apt-get -y install make && \
     apt-get -y install gcc
