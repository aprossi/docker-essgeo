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
docker run --rm -i -t -p 8888:8888 \
-v /c/Users/gerda/files-for-docker:/home/essstudent/shared-folder essanaconda:latest \
/bin/bash
```

To run a Jupyter notebook from the container shell

```
jupyter notebook
```

it should be reachable on the host machine at the IP of the VM (```XXX.XXX.XXX.XXX:8888```)

# references

* https://hub.docker.com/r/rothnic/anaconda-notebook/
  * see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
* https://hub.docker.com/r/korniichuk/jupyter-k3d-notebook/
* https://github.com/dockerfile/nginx
