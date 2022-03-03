# planner

GNOME planner for creating Gantt charts. Run by:

    docker run -it --rm -e DISPLAY=$ip:0 -v /tmp/.X11-unix:/tmp/.X11-unix -v ${PWD}:/hostpwd xaratustrah/planner


Please refer to [Fredrik Averpil's blog post](https://fredrikaverpil.github.io/2016/07/31/docker-for-mac-and-gui-applications/) in order to set up XQuartz under OSX. Please also note that the current directory has been mounted on a volume under the name `hostpwd`.
