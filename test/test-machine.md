# test dockerfile

in the same directory where this Dockerfile is, one should build with:

```
docker build -t qgis:test
```
where      qgis = name and test = version,

```
docker images
```

to run non-interactively and see a file in the mounted directory:

```
docker run --rm -t -v /Users/arossi/files-for-docker:/home/user/input-data qgis:test tree /home/user/input-data
```

this would return:

```
/home/user/input-data
`-- bubu.txt

0 directories, 1 file
```

to run interactively, the file will be in /home/user/input-data:

```
docker run --rm -i -t -v /Users/arossi/files-for-docker:/home/user/input-data qgis:test /bin/bash
````