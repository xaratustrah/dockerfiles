#FROM debian:stable-slim
FROM ubuntu:latest

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

# Installing dependencies

# RUN echo 'deb http://deb.debian.org/debian stretch main contrib non-free' >> /etc/apt/sources.list

COPY _bashrc /root/.bashrc

RUN apt-get update
RUN apt-get install -q -y --no-install-recommends software-properties-common
RUN add-apt-repository -y ppa:myriadrf/drivers
RUN apt-get update && apt-get install -q -y --no-install-recommends \
    python3-pip python3-pyqt5 python3-numpy python3-scipy \
    soapysdr-tools python3-soapysdr python-dev swig soapysdr \
    python3-soapysdr soapysdr-module-lms7 libsoapysdr-dev limesuite \
    liblimesuite-dev limesuite-udev limesuite-images \
    hamradio-sdr hamradio-tools \
    libboost-all-dev \
    gnuradio

VOLUME ["/hostpwd"]

WORKDIR /hostpwd

CMD ["bash"]
