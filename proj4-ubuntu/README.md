# Build

with the [Dockerfile](Dockerfile) available on current working directory:

```
docker build -t proj4ubuntu:latest .
```

directly from here:

```
docker build -t proj4ubuntu:latest https://raw.githubusercontent.com/anrossi/docker-essgeo/master/qgis-ubuntu/Dockerfile
```

# Run

assuming that in your home  (e..g on Mac ```/Users/myname/```, on Windows ```C:\Users\myname```) you have a directory called ```files-for-docker``` where you will copy, every week, all needed data (input and output).

## Windows7

```
docker run --rm -i -t -v /c/Users/gerda/files-for-docker:/home/essstudent/shared-folder proj4ubuntu:latest /bin/bash

```

## MacOSX

```
docker run --rm -i -t -v ~/files-for-docker:/home/essstudent/shared-folder proj4ubuntu:latest /bin/bash
```

# References

* http://wiki.ros.org/docker/Tutorials/GUI
* https://github.com/timlinux/docker-qgis-desktop
* http://stackoverflow.com/questions/25281992/alternatives-to-ssh-x11-forwarding-for-docker-containers
* http://olivier.barais.fr/blog/posts/2014.08.26/Eclipse_in_docker_container.html

