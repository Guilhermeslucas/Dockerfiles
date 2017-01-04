#a Dockerfile with some IBM development tools, like SDK, Advance
#Toolchain and XL community edition

FROM jcajka/fedora22-ppc64le
MAINTAINER Guilherme Lucas <guilherme.slucas@gmail.com>

RUN dnf install -y wget

#this plugin is needed in order to keep RPMDB ok
RUN yum install -y yum-plugin-ovl

#installing Advance Toolchain
RUN touch /etc/yum.repos.d/
COPY at9.0.repo /etc/yum.repos.d/
RUN yum install -y advance-toolchain-at9.0-runtime && yum clean all
RUN yum install -y advance-toolchain-at9.0-devel && yum clean all
RUN yum install -y advance-toolchain-at9.0-perf && yum clean all
RUN yum install -y advance-toolchain-at9.0-mcore-libs && yum clean all

#installing IBM SDK
RUN cd
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-1.10.0-1.ppc64le.rpm
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdpr_wrap-0.1.1-4.ppc64le.rpm
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdprpro-5.6.3-0.ppc64le.rpm
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/pthread-mon-0.5.11-1.ppc64le.rpm
RUN wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-remote-dependencies-1.10.0-1.ppc64le.rpm

#installing dependencies
RUN dnf install -y perl
RUN dnf install -y kernel-devel
RUN dnf install -y systemtap
RUN dnf install -y gtk2
RUN dnf install -y automake
RUN dnf install -y libtool
RUN dnf install -y gettext
RUN dnf install -y perf
RUN dnf install -y gdb
RUN dnf install -y git

#installing rpm packages
RUN rpm -ivh pthread-mon-0.5.11-1.ppc64le.rpm
RUN rpm -ivh fdprpro-5.6.3-0.ppc64le.rpm
RUN rpm -ivh fdpr_wrap-0.1.1-4.ppc64le.rpm
RUN rpm -ivh ibm-sdk-lop-1.10.0-1.ppc64le.rpm 
RUN rpm -ivh ibm-sdk-lop-remote-dependencies-1.10.0-1.ppc64le.rpm


#installing XL comunitty edition
RUN wget http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/rhel7/repodata/repomd.xml.key
RUN rpm --import repomd.xml.key
RUN wget http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/rhel7/ibm-xl-compiler-eval.repo
RUN cp ibm-xl-compiler-eval.repo /etc/yum.repos.d/
RUN yum install -y xlc.13.1.5 xlc-license-community.13.1.5 --exclude xlc-license-eval.13.1.5

#you can configure XL by typing
#/opt/ibm/xlC/13.1.5/bin/xlc_configure 
