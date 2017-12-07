FROM resin/raspberrypi3-alpine-python:latest
RUN apk add --no-cache --update git build-base autoconf automake pkgconfig curl-dev gmp-dev
RUN git clone https://github.com/magi-project/m-cpuminer-v2.git
WORKDIR /m-cpuminer-v2
RUN sed -i 's/-march=native/-mcpu=cortex-a53 -mfpu=neon-vfpv4/' Makefile.am
RUN ./autogen.sh
RUN ./configure CFLAGS="-O3" CXXFLAGS="-O3"
RUN make -j4
RUN make install
