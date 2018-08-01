# eesim

A set of tools for electronic and RF circuit simulation. You can run it by using the following command, which includes the X-forwarding. To run, just open a terminal and enter the following command:

    docker run -it --rm --name nedit -e DISPLAY=$ip:0 -v /tmp/.X11-unix:/tmp/.X11-unix -v ${PWD}:/source xaratustrah/nedit:latest
