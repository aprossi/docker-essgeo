# from https://github.com/rothnic/anaconda-notebook
# see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
FROM rothnic/anaconda-notebook
MAINTAINER apr

# install gdal
# RUN echo "deb http://ppa.launchpad.net/ubuntugis/ubuntugis-unstable/ubuntu trusty main" >> /etc/apt/sources.list
# RUN gpg --keyserver keyserver.ubuntu.com --recv 314DF160
# RUN gpg --export --armor 314DF160 | sudo apt-key add -
# RUN apt-get update -y
# RUN apt-get install libgdal1i -y

# install the rest for jupyter
RUN /bin/bash -c 'source /home/condauser/anaconda3/bin/activate python2'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install jupyter -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install pandas -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install pyproj -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install fiona -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install gdal -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/pip install fiona --upgrade'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/pip install shapely'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install basemap -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/pip install geocoder'
