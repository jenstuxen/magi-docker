FROM resin/raspberry-pi2-alpine:latest
RUN apk add --no-cache --update git build-base autoconf automake pkgconfig curl-dev gmp-dev \
 && rm -rf /var/cache/apk/* \
 && git clone https://github.com/magi-project/m-cpuminer-v2.git \
 && cd /m-cpuminer-v2 \
 && sed -i 's/-march=native/-mcpu=cortex-a7 -mfpu=neon-vfpv4/' Makefile.am \
 && ./autogen.sh \
 && ./configure CFLAGS="-O3" CXXFLAGS="-O3" \
 && make -j4 \
 && make install \
 && apk del git build-base autoconf automake pkgconfig curl-dev gmp-dev \
 && rm -rf /var/cache/apk/* \
 && rm -rf /m-cpuminer-v2
