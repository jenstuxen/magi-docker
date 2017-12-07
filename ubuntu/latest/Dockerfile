FROM ubuntu:latest
RUN apt-get update -y \
    && apt-get install -y build-essential libcurl4-openssl-dev git autotools-dev automake libgmp-dev \
    && git clone https://github.com/magi-project/m-cpuminer-v2.git \
    && cd m-cpuminer-v2/ \
    && ./autogen.sh \
    && ./configure CFLAGS="-O3" CXXFLAGS="-O3" \
    && make \
    && make install \
    && apt-get purge -y build-essential git automake autotools-dev \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/* /var/cache/apt/* \
	&& rm -rf /m-cpuminer-v2