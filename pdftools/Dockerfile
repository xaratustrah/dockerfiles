FROM archlinux

COPY packages packages

RUN pacman-key --init \
    && pacman-key --populate archlinux \
    && pacman -Syu --noconfirm
    && pacman --noconfirm --needed -S $(cat packages)

CMD ["bash"]
