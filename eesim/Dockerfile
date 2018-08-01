FROM debian:latest

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

# Installing dependencies

RUN echo 'deb http://deb.debian.org/debian stretch main contrib non-free' >> /etc/apt/sources.list

COPY _bashrc /root/.bashrc

RUN apt-get update && apt-get -y install build-essential devscripts mc

RUN apt-get -y install geda geda-utils geda-examples gerbv pcb gtkwave gnucap gspiceui ngspice kicad iverilog freehdl

# TODO: add qucs build

VOLUME ["/source"]

WORKDIR /source

CMD ["bash"]
