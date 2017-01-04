#a Dockerfile with some IBM development tools, like SDK, Advance
#Toolchain and XL community edition

FROM jcajka/fedora22-ppc64le
MAINTAINER Guilherme Lucas <guilherme.slucas@gmail.com>

RUN dnf check-update
RUN dnf install -y wget

#TO-DO: install advance toolchain e terminar sdk, ja que advance e depen

#installing IBM SDK
RUN cd
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-1.10.0-1.ppc64le.rpm
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdpr_wrap-0.1.1-4.ppc64le.rpm
RUN ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdprpro-5.6.3-0.ppc64le.rpm
RUN ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/pthread-mon-0.5.11-1.ppc64le.rpm
RUN ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-remote-dependencies-1.10.0-1.ppc64le.rpm

#installing dependencies
RUN dnf install -y perl
RUN dnf install -y kernel-devel
RUN dnf install -y systemtap

#installing rpm packages
RUN rpm -ivh pthread-mon-0.5.11-1.ppc64le.rpm
RUN rpm -ivh fdprpro-5.6.3-0.ppc64le.rpm
RUN rpm -ivh fdpr_wrap-0.1.1-4.ppc64le.rpm

#ao tentar rodar a instalação do ibm-sdk-lop, da ruim
