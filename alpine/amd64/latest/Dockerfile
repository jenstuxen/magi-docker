FROM alpine:latest
RUN apk add --no-cache --update git build-base autoconf automake pkgconfig curl-dev gmp-dev
RUN git clone https://github.com/magi-project/m-cpuminer-v2.git
WORKDIR /m-cpuminer-v2
RUN ./autogen.sh
RUN ./configure CFLAGS="-O3" CXXFLAGS="-O3"
RUN make
RUN make install