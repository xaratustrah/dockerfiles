FROM rootproject/root

RUN apt-get update && apt-get install -q -y --no-install-recommends \
python3-pip \
python3-numpy \
python3-scipy \
python3-matplotlib

RUN pip3 install setuptools pytdms uproot3

RUN cd /tmp

RUN curl https://api.github.com/repos/xaratustrah/multitaper/tags | grep "tarball_url" | grep -Eo 'https://[^\"]*' | sed  -n '1p' | xargs wget -O - | tar -xz
RUN curl https://api.github.com/repos/xaratustrah/iqtools/tags | grep "tarball_url" | grep -Eo 'https://[^\"]*' | sed  -n '1p' | xargs wget -O - | tar -xz

# make sure the dependencies do get installed. use find because we don't know the names
RUN find . -maxdepth 1 -type d -exec bash -c "cd '{}' && python3 setup.py install" \;

RUN curl https://api.github.com/repos/xaratustrah/barion/tags | grep "tarball_url" | grep -Eo 'https://[^\"]*' | sed  -n '1p' | xargs wget -O - | tar -xz
RUN curl https://api.github.com/repos/xaratustrah/iqgui/tags | grep "tarball_url" | grep -Eo 'https://[^\"]*' | sed  -n '1p' | xargs wget -O - | tar -xz

RUN find . -maxdepth 1 -type d -exec bash -c "cd '{}' && python3 setup.py install" \;

CMD ["python3"]
