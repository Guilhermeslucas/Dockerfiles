#Docker image with some IBM development tools like: IBM sdk, xl 
#community edition and advance toolchain

FROM ppc64le/ubuntu:14.04
MAINTAINER Guilherme Lucas <guilherme.slucas@gmail.com>

RUN apt-get update
RUN apt-get install wget
RUN wget ftp://ftp.unicamp.br/pub/linuxpatch/toolchain/at/ubuntu/dists/trusty/6976a827.gpg.key
RUN apt-key add 6976a827.gpg.key

#installing advance toolchain
echo deb ftp://ftp.unicamp.br/pub/linuxpatch/toolchain/at/ubuntu trusty at9.0 >> /etc/apt/sources.list   

RUN apt-get update
RUN apt-get install -y advance-toolchain-at9.0-runtime
RUN apt-get install -y advance-toolchain-at9.0-devel
RUN apt-get install -y advance-toolchain-at9.0-perf
RUN apt-get install -y advance-toolchain-at9.0-mcore-libs

#installing IBM SDK Remote Dependencies
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/deb/repo/dists/trusty/B346CA20.gpg.key
RUN apt-key add B346CA20.gpg.key

RUN echo ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/deb/repo trusty sdk >> /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y ibm-sdk-lop
RUN apt-get install -y ibm-sdk-lop-remote-dependencies
