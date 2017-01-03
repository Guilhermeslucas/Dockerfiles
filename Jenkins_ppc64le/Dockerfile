FROM ppc64le/ubuntu:14.04
MAINTAINER  Guilherme Lucas <guilherme.slucas@gmail.com>
RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y nginx
RUN apt-get install -y openjdk-7-jdk
RUN wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
RUN sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
RUN apt-get update
RUN apt-get -y install Jenkins
RUN apt-get -y install git
RUN apt-get -y install make
RUN apt-get -y install gcc
