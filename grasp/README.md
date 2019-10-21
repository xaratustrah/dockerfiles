# GRASP2018

A dockerfile for [GRASP2018](https://github.com/compas/grasp)

Build with:

    docker build -t xaratustrah/grasp .

and run by:

    docker run -it --rm -e DISPLAY=$ip:0 -v /tmp/.X11-unix:/tmp/.X11-unix -v ${PWD}:/source xaratustrah/grasp

before that you have to export your display IP. On OSX it goes like this:

    open -a XQuartz && ip=$(ifconfig en6 | grep inet | awk '$1=="inet" {print $2}') && xhost + $ip

where `en6` is the name of your network interface, so please change it accordingly.

You can overwrite the default command and enter the shell by adding`/bin/bash` add the end of the run command.
