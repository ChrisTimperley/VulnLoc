FROM ubuntu:16.04

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
      bison \
      build-essential \
      flex \
      git \
      ipython \
      libtool \
      python-dev \
      python-pip \
      texinfo \
      unzip \
      vim \
      zip \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace
ARG SUT_SOURCE_PATH=/workspace/source
RUN git clone git://sourceware.org/git/binutils-gdb.git "${SUT_SOURCE_PATH}"
ARG SUT_VERSION=7a31b38ef87d133d8204cae67a97f1989d25fa18
RUN git -C "${SUT_SOURCE_PATH}" checkout "${SUT_VERSION}"

COPY exploit exploit
COPY build build
COPY prebuild prebuild
COPY test test
