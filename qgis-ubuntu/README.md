# Build

with the [Dockerfile](Dockerfile) available on current working directory:

```
docker build -t essqgis:latest .
```

directly from here:

```
docker build -t essqgis:latest https://raw.githubusercontent.com/anrossi/210222-Spring2016/master/qgis-ubuntu/Dockerfile
```

# Run

```
docker run --rm -i -t -v ~/files-for-docker:/home/essstudent/shared-folder essqgis:latest /bin/bash
```
## Shared folders

### Shared folder in MacOSX

e.g. a directory in the ```$HOME``` can be mounted on the container filesystem with the option:

```
-v ~/files-for-docker:/home/essstudent/shared-folder
````

### Shared folder in Windows 7

e.g. a directory in the Home directory of the user (e.g. Gerda) can be mounted on the container filesystem with the option:

```
-v /c/Users/gerda:/home/essstudent/shared-folder
````

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
root@........:/# qgis
```

and Qgis Desktop should launch.

once all is over xhost can be turned off with:

```
xhost -
```

## Windows7

Similar procedure, instead of XQuart, one can use a Windows X11 Server, e.g. Xming (http://sourceforge.net/projects/xming/)

With Xming on (and accepting connections) one can launch QGIS (or any X11), first connecting:

```
docker run --rm -i -t -v /c/Users/gerda/files-for-docker:/home/essstudent/shared-folder \
-e DISPLAY=XXX.XXX.XXX.XXX:0 \
essqgis:latest
```

from the container shell:

```
root@........:/# qgis
```

# References

* http://wiki.ros.org/docker/Tutorials/GUI
* https://github.com/timlinux/docker-qgis-desktop
* http://stackoverflow.com/questions/25281992/alternatives-to-ssh-x11-forwarding-for-docker-containers
* http://olivier.barais.fr/blog/posts/2014.08.26/Eclipse_in_docker_container.html

