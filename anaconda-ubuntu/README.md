# build

with the [Dockerfile](Dockerfile) available on current working directory:

```
docker build -t essanaconda:latest .
```

directly from here:

```
docker build -t essanaconda:latest https://raw.githubusercontent.com/anrossi/docker-essgeo/master/anaconda-ubuntu/Dockerfile
```


# to enter the machine 
```
docker run --rm -i -t -p 8888:8888 -e DISPLAY=XXX.XXX.XXX.XXX:0 \
-v /c/Users/gerda/files-for-docker:/home/essstudent/shared-folder essanaconda:latest \
/bin/bash
```
where ```XXX.XXX.XXX.XXX``` is the IP of the host  (yellow post-it)

To run a Jupyter notebook from the container shell

(redundat, but just in case..)

```
export DISPLAY=XXX.XXX.XXX.XXX:0
export PATH=/opt/conda/bin:$PATH
```

and then 
```
jupyter notebook
```

will open a browser window on the X server

it should also be reachable on the host machine at the IP of the VM (```YYY.YYY.YYY.YYY:8888```)

# references

* https://hub.docker.com/r/rothnic/anaconda-notebook/
  * see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
* https://hub.docker.com/r/korniichuk/jupyter-k3d-notebook/
* https://github.com/dockerfile/nginx
