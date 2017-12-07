FROM alpine:latest
RUN apk add --no-cache --update git build-base autoconf automake pkgconfig curl-dev gmp-dev \
 && rm -rf /var/cache/apk/* \
 && git clone https://github.com/magi-project/m-cpuminer-v2.git \
 && cd /m-cpuminer-v2 \
 && ./autogen.sh \
 && ./configure CFLAGS="-O3" CXXFLAGS="-O3" \
 && make \
 && make install \
 && apk del git build-base autoconf automake pkgconfig \
 && rm -rf /var/cache/apk/* \
 && rm -rf /m-cpuminer-v2
