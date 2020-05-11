FROM rootproject/root-archlinux

RUN cd /tmp \
    && git clone git://github.com/rootpy/rootpy.git \
    && git clone git://github.com/xaratustrah/multitaper.git \
    && git clone git://github.com/xaratustrah/iqtools.git


COPY packages packages

USER 0

RUN pacman -Syu --noconfirm \
    && pacman --noconfirm --needed -S $(cat packages)

RUN pip install pytdms \
    && cd /tmp/rootpy \
    && python setup.py install \
    && cd /tmp/multitaper \
    && python setup.py install \
    && cd /tmp/iqtools \
    && python setup.py install

# go back to regular user
USER docker-user

CMD ["/bin/bash"]
