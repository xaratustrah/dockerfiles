FROM archlinux

COPY packages packages

RUN pacman-key --init \
    && pacman-key --populate archlinux \
    && pacman -Syu --noconfirm \
    && pacman --noconfirm --needed -S $(cat packages) \\
    && ln -s /usr/bin/vendor_perl/exiftool /bin/exiftool

CMD ["bash"]
