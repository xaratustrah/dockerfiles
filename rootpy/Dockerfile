FROM rootproject/root-archlinux

COPY packages packages

RUN pacman-key --init \
    && pacman-key --populate archlinux \
    && pacman -Syu --noconfirm \
    && pacman --noconfirm --needed -S $(cat packages)

RUN pip install pytdms \
    && cd /tmp \
    && git clone git://github.com/rootpy/rootpy.git \
    && cd rootpy \
    && python setup.py install \
    && cd /tmp \
    && git clone git://github.com/xaratustrah/multitaper.git \
    && cd multitaper \
    && python setup.py install \
    && cd /tmp \
    && git clone git://github.com/xaratustrah/iqtools.git \
    && cd iqtools \
    && python setup.py install

CMD ["/bin/bash"]
