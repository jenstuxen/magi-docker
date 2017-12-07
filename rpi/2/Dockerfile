FROM resin/raspberrypi2-alpine-python:latest
RUN apk install --no-cache git
RUN git clone https://github.com/magi-project/m-cpuminer-v2.git
WORKDIR /m-cpuminer-v2
RUN sed -i 's/-march=native/-mcpu=cortex-a7 -mfpu=neon-vfpv4/' Makefile.am
RUN ./autogen.sh
RUN ./configure CFLAGS="-O3" CXXFLAGS="-O3"
RUN make -j4
RUN make install