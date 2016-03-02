# from https://github.com/rothnic/anaconda-notebook
# see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
# TAKEN FROM FROM rothnic/anaconda-notebook
######################################
# FROM ubuntu:latest
FROM continuumio/anaconda
MAINTAINER apr
EXPOSE 8888

# # install gdal
# USER root
# RUN echo "deb http://ppa.launchpad.net/ubuntugis/ubuntugis-unstable/ubuntu trusty main" >> /etc/apt/sources.list
# RUN gpg --keyserver keyserver.ubuntu.com --recv 314DF160
# RUN gpg --export --armor 314DF160 | apt-key add -
# RUN apt-get update -y
# # RUN apt-get install libgdal-dev libgdal1-dev  -y
# RUN apt-get install libgdal1h -y

# # install the rest for jupyter
# USER condauser
USER root
# RUN /bin/bash -c '/opt/conda/bin/conda install jupyter -y'
RUN /bin/bash -c '/opt/conda/bin/conda install pandas -y'
RUN /bin/bash -c '/opt/conda/bin/conda install pyproj -y'
RUN /bin/bash -c '/opt/conda/bin/conda install fiona -y'
RUN /bin/bash -c '/opt/conda/bin/conda install gdal -y'
# RUN /bin/bash -c '/opt/conda/bin/pip install fiona --upgrade'
RUN /bin/bash -c '/opt/conda/bin/pip install shapely'
RUN /bin/bash -c '/opt/conda/bin/condaa install basemap -y'
RUN /bin/bash -c '/opt/conda/bin/pip install geocoder'

# /opt/conda/bin/easy_install
