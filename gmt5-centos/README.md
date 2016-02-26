# build

with the [Dockerfile](Dockerfile) available on current working directory:

```
docker build -t essgmt5:latest .
```

directly from here:

```
docker build -t essgmt5:latest https://raw.githubusercontent.com/anrossi/docker-essgeo/master/gmt5-centos/Dockerfile
```

# run on Windows
```
docker run --rm -i -t -v /c/Users/gerda/files-for-docker:/home/essstudent/shared-folder essgmt5:latest /bin/bash
```

# test
* run the container
* go in the shared folder ```cd /home/essstudent/shared-folder```
* use a GMT example e.g. from http://gmt.soest.hawaii.edu/doc/latest/gallery/ex26.html#example-26
* run it e.g. as example.sh
    * editing with ```nano example.sh``` inside ```/home/essstudent/shared-folder ```
    * pasting the content from example-26 above
    * making the file executable with ```chmod +x example.sh```
    * running ```./example.sh```  inside ```/home/essstudent/shared-folder ```
* exit the container
* locate the shared directory on the host, e.g. ```~/files-for-docker``` and make sure the output of example-25 (some postscript file) is there
* it works (or it seems to)...
