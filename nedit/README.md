# nedit

A simple nice motif based editor. You can run it by using the following command, which includes the X-forwarding. To run, just open a terminal and enter the following command:

    docker run -it --rm --name nedit -e DISPLAY=$ip:0 -v /tmp/.X11-unix:/tmp/.X11-unix -v ${PWD}:/source xaratustrah/nedit:latest

Please refer to [Fredrik Averpil's blog post](https://fredrikaverpil.github.io/2016/07/31/docker-for-mac-and-gui-applications/) in order to set up XQuartz under OSX. Please also note that the current directory has been mounted on a volume.
