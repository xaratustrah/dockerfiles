# analysistools

A docker image for particle accelerator storage ring physics, based on PyROOT and [ROOT](https://root.cern/) and some other code, such as:

* [iqtools](https://github.com/xaratustrah/iqtools)
* [barion](https://github.com/xaratustrah/barion)
* [lisereader](https://github.com/gwgwhc/lisereader)
* [rionid](https://github.com/DFreireF/rionid)

Build with:

    docker build -t xaratustrah/analysistools .


Now you can use the individual commands, either by typing a long command invoking docker, or by first making aliases for simple use, such as:

```bash
alias iqtools="docker run --rm --volume "$(pwd):/pwd" --user $(id -u):$(id -g) xaratustrah/analysistools iqtools"
alias lisereader="docker run --rm --volume "$(pwd):/pwd" --user $(id -u):$(id -g) xaratustrah/analysistools lisereader"
alias rionid="docker run --rm --volume "$(pwd):/pwd" --user $(id -u):$(id -g) xaratustrah/analysistools rionid"
```

then use the alias, for example:

```bash
iqtools --nframes 400 --lframes 1024 -g /pwd/p_400_MeV_u_332_uA_0.tiq
```

this also works for GUI apps. Under Linux you can do:

```bash
alias iqgui="xhost + && docker run -it --rm -e --volume '$(pwd):/pwd' --user $(id -u):$(id -g) DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix xaratustrah/analysistools iqgui && xhost -"
alias barion="xhost + && docker run -it --rm -e --volume '$(pwd):/pwd' --user $(id -u):$(id -g) DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix xaratustrah/analysistools barion && xhost -"
```

then just run the command:

```bash
iqgui
```
or
```bash
barion
```
