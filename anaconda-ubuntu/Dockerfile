# FROM rothnic/anaconda-notebook
FROM continuumio/anaconda
MAINTAINER apr
EXPOSE 8888

RUN /bin/bash -c '/opt/conda/bin/conda install jupyter -y'
RUN /bin/bash -c '/opt/conda/bin/conda install pandas -y'
RUN /bin/bash -c '/opt/conda/bin/conda install basemap -y'
RUN /bin/bash -c '/opt/conda/bin/conda install pyproj -y'
RUN /bin/bash -c '/opt/conda/bin/conda install fiona -y'
RUN /bin/bash -c '/opt/conda/bin/conda install gdal -y'
RUN /bin/bash -c '/opt/conda/bin/conda install -c https://conda.anaconda.org/unidata shapely -y'
RUN /bin/bash -c '/opt/conda/bin/pip install geocoder'

# add browser
RUN /bin/bash -c 'apt-get update --fix-missing'
RUN /bin/bash -c 'apt-get install iceweasel --force -y'


# RUN /bin/bash -c 'source /home/condauser/anaconda3/bin/activate python2'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install jupyter -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install pandas -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install basemap -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install pyproj -y'
# RUN /bin/bash -c '//home/condauser/anaconda3/envs/python2/bin/conda install fiona -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install gdal -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/conda install -c https://conda.anaconda.org/unidata shapely -y'
# RUN /bin/bash -c '/home/condauser/anaconda3/envs/python2/bin/pip install geocoder'
