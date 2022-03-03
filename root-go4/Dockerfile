# A docker container with GO4

# More info on GO4
# http://web-docs.gsi.de/%7Ego4/download/go4.php

# based on https://hub.docker.com/r/rootproject/root-ubuntu16/

FROM rootproject/root-ubuntu16:latest

ENV VERSION 6.0.0
ENV GO4_FILE go4-${VERSION}
ENV GO4_URL http://web-docs.gsi.de/~go4/download/${GO4_FILE}.tar.gz

RUN sudo apt-get update && sudo apt-get install -q -y --no-install-recommends \
  wget \
  build-essential \
  module-init-tools \
  qt4-qmake

RUN sudo ln -s /usr/share/qt4/bin/qmake /bin/qmake
RUN cd /opt && \
  sudo wget $GO4_URL && \
  sudo tar xzvf  ${GO4_FILE}.tar.gz && \
  cd ${GO4_FILE} && sudo make

# ENV PATH=$PATH

# run bash
CMD ["/opt/go4-${VERSION}/bin/go4"]
