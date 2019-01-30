# root-go4

A dockerfile for [CERN ROOT](https://root.cern.ch/) + [GSI GO4](http://web-docs.gsi.de/%7Ego4/download/go4.php)

Build with:

    docker build -t xaratustrah/root-go4 .

and run by:

    docker run -it --rm -e DISPLAY=$ip:0 -v /tmp/.X11-unix:/tmp/.X11-unix -v ${PWD}:/source xaratustrah/root-go4

before that you have to export your display IP. On OSX it goes like this:

    open -a XQuartz && ip=$(ifconfig en6 | grep inet | awk '$1=="inet" {print $2}') && xhost + $ip

where `en6` is the name of your network interface.


You can overwrite the default command and enter the shell by adding`/bin/bash` add the end of the run command.
