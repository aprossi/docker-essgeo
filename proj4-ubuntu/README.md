# Build

with the [Dockerfile](Dockerfile) available on current working directory:

```
docker build -t proj4ubuntu:latest .
```

directly from here:

```
docker build -t proj4ubuntu:latest https://raw.githubusercontent.com/anrossi/210222-Spring2016/master/proj4-ubuntu/Dockerfile
```

# Run

assuming that in your home  (e..g on Mac ```/Users/myname/```) you have a directory called ```files-for-docker``` where you will copy, every week, all needed data (input and output).

```
docker run --rm -i -t -v ~/files-for-docker:/home/essstudent/shared-folder proj4ubuntu:latest /bin/bash
```

# X11 forwarding

in order. On host (anywhere, e.g. on docker shell):

## MacOSX

Xquartz should be running with both ticks enabled in security tab (see references)

```
xhost +
```

on docker shell:

```
docker run --rm -i -t -v ~/files-for-docker:/home/essstudent/shared-folder \
-e DISPLAY=XXX.XXX.XXX.XXX:0 \
essqgis:latest
```

where ```XXX.XXX.XXX.XXX``` is the IP of the host

from the container shell:

```
qgis
```

and Qgis Desktop should launch.

once all is over xhost can be turned off with:

```
xhost -
```

## Windows7

* use Xming from http://sourceforge.net/projects/xming/


# References

* http://wiki.ros.org/docker/Tutorials/GUI
* https://github.com/timlinux/docker-qgis-desktop
* http://stackoverflow.com/questions/25281992/alternatives-to-ssh-x11-forwarding-for-docker-containers
* http://olivier.barais.fr/blog/posts/2014.08.26/Eclipse_in_docker_container.html

