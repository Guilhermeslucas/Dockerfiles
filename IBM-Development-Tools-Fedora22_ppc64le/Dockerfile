#a Dockerfile with some IBM development tools, like SDK, Advance
#Toolchain and XL community edition

FROM jcajka/fedora22-ppc64le
MAINTAINER Guilherme Lucas <guilherme.slucas@gmail.com>

run dnf install -y wget && \
    yum install -y yum-plugin-ovl && \
    touch /etc/yum.repos.d/

COPY at9.0.repo /etc/yum.repos.d/

RUN  yum install -y advance-toolchain-at9.0-runtime && yum clean all && \
     yum install -y advance-toolchain-at9.0-devel && yum clean all && \
     yum install -y advance-toolchain-at9.0-perf && yum clean all && \
     yum install -y advance-toolchain-at9.0-mcore-libs && yum clean all && \
     cd && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-1.10.0-1.ppc64le.rpm && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdpr_wrap-0.1.1-4.ppc64le.rpm && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/fdprpro-5.6.3-0.ppc64le.rpm && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/pthread-mon-0.5.11-1.ppc64le.rpm && \
     wget ftp://public.dhe.ibm.com/software/server/iplsdk/v1.10.0/packages/rpm/ibm-sdk-lop-remote-dependencies-1.10.0-1.ppc64le.rpm && \
     dnf install -y perl && \
     dnf install -y kernel-devel && \
     dnf install -y systemtap && \
     dnf install -y gtk2 && \
     dnf install -y automake && \
     dnf install -y libtool && \
     dnf install -y gettext && \
     dnf install -y perf && \
     dnf install -y gdb && \
     dnf install -y git && \
     rpm -ivh pthread-mon-0.5.11-1.ppc64le.rpm && \
     rpm -ivh fdprpro-5.6.3-0.ppc64le.rpm && \
     rpm -ivh fdpr_wrap-0.1.1-4.ppc64le.rpm && \
     rpm -ivh ibm-sdk-lop-1.10.0-1.ppc64le.rpm && \
     rpm -ivh ibm-sdk-lop-remote-dependencies-1.10.0-1.ppc64le.rpm && \
     wget http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/rhel7/repodata/repomd.xml.key && \
     rpm --import repomd.xml.key && \
     wget http://public.dhe.ibm.com/software/server/POWER/Linux/xl-compiler/eval/ppc64le/rhel7/ibm-xl-compiler-eval.repo && \
     cp ibm-xl-compiler-eval.repo /etc/yum.repos.d/ && \
     yum install -y xlc.13.1.5 xlc-license-community.13.1.5 --exclude xlc-license-eval.13.1.5 && \
