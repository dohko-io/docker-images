FROM ubuntu:16.04

LABEL Description="This is an image to build the FLOW*: a verification tool for cyber-physical systems (flowstar.org)"

ENV PATH="/opt/flowstar:${PATH}"

RUN apt-get update -y  && \
    apt-get install -yq bison \
                        build-essential \ 
 						wget \
						libgsl-dev \
						libglpk-dev \
						libbison-dev \
						gnuplot \
						help2man \
						libmpfr-dev \
						libtool \
						automake \
						autotools-dev \
						libltdl-dev \
						libtool \
						autoconf \
						autopoint && \
	cd /tmp && wget https://github.com/westes/flex/releases/download/v2.6.4/flex-2.6.4.tar.gz && \
	tar xzf flex-2.6.4.tar.gz && rm -f flex-2.6.4.tar.gz && \
	cd flex-2.6.4 && ./autogen.sh && ./configure && make && make install && \
	cd /tmp && wget https://www.cs.colorado.edu/~xich8622/src/flowstar-2.1.0.tar.gz && \
	tar xzf flowstar-2.1.0.tar.gz && rm -f flowstar-2.1.0.tar.gz && \
	cd flowstar-2.1.0 && make && \
	cd /tmp && mv /tmp/flowstar-2.1.0 /opt && \
	ln -s /opt/flowstar-2.1.0/ /opt/flowstar && \
	rm -rf /var/lib/apt/lists/* && \
	rm -rf /tmp/*
						