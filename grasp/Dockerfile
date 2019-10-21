# A docker container for GRASP

FROM debian:stable-slim

ENV   FC gfortran
ENV   FC_FLAGS "-O2 -fno-automatic "
ENV   FC_LD " "
ENV   GRASP "/opt/grasp"
ENV   LAPACK_LIBS "-llapack -lblas"
ENV   FC_MPI "mpifort"
ENV   FC_MPIFLAGS "${FC_FLAGS}"
ENV   FC_MPILD ${FC_LD}
ENV   MPI_TMP "${HOME}/grasp_mpi_tmp"
ENV   PATH "/opt/grasp/bin:$PATH"


RUN apt-get update && apt-get install -q -y --no-install-recommends \
  apt-utils \
  git \
  build-essential \
  gfortran \
  openmpi-bin \
  openmpi-common \
  libopenmpi-dev \
  ca-certificates \
  octave

RUN update-ca-certificates
RUN ln -s /usr/lib/x86_64-linux-gnu/blas/libblas.so.3.8.0 /usr/lib/libblas.so
RUN ln -s /usr/lib/x86_64-linux-gnu/lapack/liblapack.so.3.8.0 /usr/lib/liblapack.so

RUN cd /opt && \
  git clone https://github.com/compas/grasp.git && \
  cd grasp/src && \
  make clean && \
  make
