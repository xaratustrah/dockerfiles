FROM rootproject/root

RUN apt-get update && apt-get install -q -y --no-install-recommends \
python3-pip \
python3-numpy \
python3-scipy \
python3-matplotlib \
python3-pyqt5

RUN pip3 install --upgrade pip \
    && pip3 install --root-user-action=ignore setuptools

RUN mkdir /tmp/analysistools \
    && cd "$_" \
    && curl -LkSs https://api.github.com/repos/xaratustrah/iqtools/tarball | tar xz -C ./ \
    && curl -LkSs https://api.github.com/repos/xaratustrah/barion/tarball | tar xz -C ./ \
    && curl -LkSs https://api.github.com/repos/gwgwhc/lisereader/tarball | tar xz -C ./ \
    && curl -LkSs https://api.github.com/repos/DFreireF/rionid/tarball | tar xz -C ./ \
    && find . -maxdepth 1 -type d -exec bash -c "cd '{}' && pip3 install --root-user-action=ignore -r requirements.txt" \; \
    && find . -maxdepth 1 -type d -exec bash -c "cd '{}' && pip3 install --root-user-action=ignore ." \; \
    && rm -rf /tmp/analysistools

CMD ["/bin/bash"]
