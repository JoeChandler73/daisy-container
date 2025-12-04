FROM --platform=linux/amd64 debian:stable-slim

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    git \
    build-essential \
    dfu-util \
    openocd \
    wget \
    bzip2 \
    usbutils \
    && rm -rf /var/lib/apt/lists/*

# Download and install the specific ARM toolchain version (10-2020-q4-major)
WORKDIR /tmp
RUN wget --no-check-certificate -q https://developer.arm.com/-/media/Files/downloads/gnu-rm/10-2020q4/gcc-arm-none-eabi-10-2020-q4-major-x86_64-linux.tar.bz2 && \
    tar -xjf gcc-arm-none-eabi-10-2020-q4-major-x86_64-linux.tar.bz2 -C /opt && \
    rm gcc-arm-none-eabi-10-2020-q4-major-x86_64-linux.tar.bz2

# Set up the ARM toolchain path
ENV GCC_PATH=/opt/gcc-arm-none-eabi-10-2020-q4-major/bin
ENV PATH=$GCC_PATH:$PATH