#Docker image with some IBM development tools like: IBM sdk, xl
#community edition and advance toolchain

FROM ppc64le/ubuntu:14.04
MAINTAINER Guilherme Lucas <guilherme.slucas@gmail.com>

RUN  apt-get update && \
     apt-get install -y wget && \
     wget ftp://ftp.unicamp.br/pub/linuxpatch/toolchain/at/ubuntu/dists/trusty/6976a827.gpg.key && \
     apt-key add 6976a827.gpg.key && \
     echo deb ftp://ftp.unicamp.br/pub/linuxpatch/toolchain/at/ubuntu trusty at9.0 >> /etc/apt/sources.list && \
     apt-get update && \
     apt-get install -y advance-toolchain-at9.0-runtime && \
     apt-get install -y advance-toolchain-at9.0-devel && \
     apt-get install -y advance-toolchain-at9.0-perf && \
     apt-get install -y advance-toolchain-at9.0-mcore-libs && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/deb/repo/dists/trusty/B346CA20.gpg.key && \
     apt-key add B346CA20.gpg.key && \
     echo deb ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/deb/repo trusty sdk >> /etc/apt/sources.list && \
     apt-get update && \
     apt-get install -y ibm-sdk-lop && \
     apt-get install -y ibm-sdk-lop-remote-dependencies && \
     wget -q http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/ubuntu/public.gpg -O- | apt-key add - && \
     echo "deb http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/ubuntu/ trusty main" | tee /etc/apt/sources.list.d/ibm-xl-compiler-eval.list && \
     apt-get update && \
     apt-get install -y xlc.13.1.5
