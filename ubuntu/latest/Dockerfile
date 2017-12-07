FROM ubuntu:latest
RUN apt-get update -y \
    && apt-get install -y build-essential libcurl4-openssl-dev git autotools-dev automake libgmp-dev \
    && rm -rf /var/lib/apt/lists/* /var/cache/apt/*
RUN git clone https://github.com/magi-project/m-cpuminer-v2.git
WORKDIR /m-cpuminer-v2
RUN ./autogen.sh
RUN ./configure CFLAGS="-O3" CXXFLAGS="-O3"
RUN make
RUN make install