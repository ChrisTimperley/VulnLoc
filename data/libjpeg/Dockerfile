FROM ubuntu:16.04

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
      autoconf \
      automake \
      autopoint \
      bison \
      build-essential \
      clang \
      flex \
      gettext \
      git \
      gperf \
      ipython \
      libtool \
      nasm \
      pkg-config \
      python-dev \
      python-pip \
      rsync \
      texinfo \
      unzip \
      vim \
      zip \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace

ARG SUT_REPO_URL=https://github.com/libjpeg-turbo/libjpeg-turbo.git
ARG SUT_SOURCE_PATH=/workspace/source
RUN git clone "${SUT_REPO_URL}" "${SUT_SOURCE_PATH}"


COPY build build
COPY prebuild prebuild

ARG SUT_VERSION
RUN git -C "${SUT_SOURCE_PATH}" checkout "${SUT_VERSION}" \
 && cd "${SUT_SOURCE_PATH}" \
 && autoreconf -fiv

ARG BUG_DIR
COPY "${BUG_DIR}/exploit" exploit
COPY "${BUG_DIR}/test" test
