# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

FROM centos:7.5.1804

LABEL maintainer=wutao

ARG RELEASE_VERSION=v2.3.0

RUN yum -y install centos-release-scl \
scl-utils \
epel-release; \
yum -y install devtoolset-7-gcc \
devtoolset-7-gcc-c++ \
java-1.8.0-openjdk-devel.x86_64 \
python3 \
automake \
autoconf \
make \
libtool \
git \
file \
wget \
ccache \
nmap-ncat \
zip \
gdb \
vim \
unzip \
which \
openssl-devel \
libaio-devel \
snappy-devel \
bzip2-devel \
zlib \
zlib-devel \
libzstd-devel \
lz4-devel \
bison \
maven \
flex \
patch; \
yum clean all; \
rm -rf /var/cache/yum;

RUN pip3 install --no-cache-dir cmake

ENV PATH="/opt/rh/devtoolset-7/root/bin/:${PATH}"

RUN git clone --recursive --branch $RELEASE_VERSION --depth=1 https://github.com/apache/incubator-pegasus.git  \
    && cd incubator-pegasus \
    && ./run.sh build -c -j $(($(nproc)/2+1))

WORKDIR /root/pegasus
