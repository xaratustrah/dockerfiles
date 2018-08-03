FROM debian:stable-slim

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

# Installing dependencies

RUN echo 'deb http://deb.debian.org/debian stretch main contrib non-free' >> /etc/apt/sources.list

COPY _bashrc /root/.bashrc

RUN apt-get update && apt-get -y install build-essential devscripts mc net-tools

RUN apt-get -y install hamradio-sdr hamradio-tools

VOLUME ["/hostpwd"]

WORKDIR /hostpwd

CMD ["bash"]
