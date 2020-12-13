FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    libc6-dev ca-certificates \
    libc6-dev-armel-cross qemu-user-static curl xz-utils software-properties-common

RUN add-apt-repository ppa:team-gcc-arm-embedded/ppa && \
    apt-get update && \
    apt-get install -y --no-install-recommends gcc-arm-embedded

RUN curl -L https://developer.arm.com/-/media/Files/downloads/gnu-a/9.2-2019.12/binrel/gcc-arm-9.2-2019.12-x86_64-aarch64-none-elf.tar.xz | tar --extract --xz --strip 1 --directory /usr/local

ENV CC_aarch64_unknown_none_softfloat=aarch64-none-elf-gcc \
    CFLAGS_aarch64_unknown_none_softfloat=-mstrict-align -march=armv8-a+nofp+nosimd \
