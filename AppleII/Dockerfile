FROM debian
MAINTAINER retrocontainer <retrocontainer@retrocontainer.net>

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
ENTRYPOINT ["/opt/appleII/linapple_src-2b/linapple"]




#                          .8 
#                        .888
#                      .8888'
#                     .8888'
#                     888'
#                       8'
#        .88888888888. .88888888888.
#     .8888888888888888888888888888888.
#   .8888888888888888888888888888888888.
#  .&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&'
#  &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&'
#  &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&'
#  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@:
#  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@:
#  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@:
#  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%.
#  %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%.
#  `%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%.
#   `00000000000000000000000000000000000'
#    `000000000000000000000000000000000'
#     `0000000000000000000000000000000'
#       `###########################'
#         `#######################'
#           `#########''########'
#             `""""""'  `"""""'
