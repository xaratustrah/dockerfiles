FROM python:3.7-slim

# Set environmental variables

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

COPY _bashrc /root/.bashrc

#RUN apk add bash

RUN pip install numpy scipy matplotlib pypdf2

# run bash
CMD ["/bin/bash"]
