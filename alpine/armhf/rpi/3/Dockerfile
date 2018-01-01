FROM resin/raspberrypi3-alpine:latest
#build arm packages using qemu on dockerhub
RUN [ "cross-build-start" ]
RUN apk add --no-cache --update git build-base autoconf automake pkgconfig curl-dev gmp-dev \
 && rm -rf /var/cache/apk/* \
 && git clone https://github.com/magi-project/m-cpuminer-v2.git \
 && cd /m-cpuminer-v2 \
 && sed -i 's/-march=native/-mcpu=cortex-a53 -mfpu=neon-fp-armv8 -funsafe-math-optimizations /' Makefile.am \
 && ./autogen.sh \
 && ./configure CFLAGS="-O3" CXXFLAGS="-O3" \
 && make -j4 \
 && make install \
 && apk del git build-base autoconf automake pkgconfig \
 && rm -rf /var/cache/apk/* \
 && rm -rf /m-cpuminer-v2
RUN [ "cross-build-end" ]  