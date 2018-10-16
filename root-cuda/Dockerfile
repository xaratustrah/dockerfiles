# A docker container with the Nvidia kernel module and CUDA drivers installed

# based on https://hub.docker.com/r/rootproject/root-ubuntu16/
# based on https://hub.docker.com/r/tleyden5iwx/ubuntu-cuda/

FROM rootproject/root-ubuntu16:latest

ARG CUDA_FILE='cuda_10.0.130_410.48_linux'

ENV CUDA_RUN https://developer.nvidia.com/compute/cuda/10.0/Prod/local_installers/$CUDA_FILE

RUN sudo apt-get update && sudo apt-get install -q -y \
  wget \
  build-essential \
  module-init-tools

RUN cd /opt && \
  sudo wget $CUDA_RUN && \
  sudo mkdir -p nvidia_installers/tmp && \
  sudo /bin/sh ./$CUDA_FILE -extract=`pwd`/nvidia_installers && \
  cd nvidia_installers && \
  sudo /bin/sh ./NVIDIA-Linux-x86_64-410.48.run -s --no-kernel-module && \
  sudo /bin/sh ./cuda-linux.10.0.130-24817639.run -noprompt -tmpdir ./tmp && \
  sudo /bin/sh ./cuda-samples.10.0.130-24817639-linux.run -noprompt -prefix=/home/builder/cuda_samples -cudaprefix=/usr/local/cuda-10.0/

# some clean up

RUN sudo chown -R builder:builder /home/builder && \
  sudo rm -rf /opt/nvidia_installers /opt/$CUDA_FILE

# Ensure the CUDA libs and binaries are in the correct environment variables
ENV LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.0/lib64
ENV PATH=$PATH:/usr/local/cuda-10.0/bin

# run bash
CMD ["/bin/bash"]
