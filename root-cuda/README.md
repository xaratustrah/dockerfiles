# root-cuda

CERN ROOT + NVIDIA CUDA libraries. Run on GPU by:

    docker run -ti --rm --name root-cuda -v ${PWD}:/source --device /dev/nvidia0:/dev/nvidia0 --device /dev/nvidia1:/dev/nvidia1 --device /dev/nvidia2:/dev/nvidia2 --device /dev/nvidia3:/dev/nvidia3 --device /dev/nvidiactl:/dev/nvidiactl --device /dev/nvidia-uvm:/dev/nvidia-uvm
