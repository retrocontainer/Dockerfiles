FROM debian
MAINTAINER nils <nils@datenvandalismus.org>

RUN apt-get update && apt-get install -y \
        x11-apps \
        build-essential \
        libcurl4-openssl-dev \
        zlib1g-dev \
        libzip-dev \
        libsdl1.2-dev \
        wget \
        bzip2 \
        make \
        --no-install-recommends \
        && rm -rf /var/lib/apt/lists/*

RUN mkdir /opt/appleII
RUN cd /opt/appleII
WORKDIR /opt/appleII/
RUN /usr/bin/wget http://beotiger.com/download/linapple_src-2b
RUN mv linapple_src-2b linapple_src-2b.tar.bz2
RUN bunzip2 linapple_src-2b.tar.bz2
RUN tar xvf linapple_src-2b.tar
RUN pwd
RUN cd /opt/appleII/linapple_src-2b/src
RUN make -C /opt/appleII/linapple_src-2b/src all;

WORKDIR /opt/appleII/linapple_src-2b
COPY linapple.conf /opt/appleII/linapple_src-2b/linapple.conf
# RUN make & make install
# RUN make
# RUN cd /opt/appleII/linapple_src-2b/src
# RUN make install;
ENTRYPOINT ["/opt/appleII/linapple_src-2b/linapple"]
# CMD /bin/bash
