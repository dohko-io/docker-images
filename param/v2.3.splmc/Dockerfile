FROM ubuntu:16.04

LABEL Description="This is an image to build the PARAMetric Markov Model Analyzer (PARAM Tool v2.3)"

RUN apt-get update -y  && \
    apt-get install -yq bison \
                        build-essential \
                        flex \ 
                        ginac-tools \
                        git \
                        libginac-dev \
                        libboost-all-dev \
                        wget && \
    wget http://luajit.org/download/LuaJIT-2.0.5.tar.gz && \
    tar xzvf LuaJIT-2.0.5.tar.gz && \
	rm -f LuaJIT-2.0.5.tar.gz && \
	cd LuaJIT-2.0.5 && \
	make && make install && \
	cd .. && rm -rf LuaJIT-2.0.5 && \
    git clone https://github.com/SPLMC/param.git && \
    cd param && make && \
    mkdir -p /opt/param && mv param /opt/param && \
    ln -s /opt/param/param /usr/bin/param && \
    cd .. && rm -rf param && \
    apt-get --purge -y remove   bison \
                                build-essential \
                                flex \ 
                                ginac-tools \
                                git \
                                libginac-dev \
                                libboost-all-dev \
                                wget && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*
