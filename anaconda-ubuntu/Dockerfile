FROM rothnic/anaconda-notebook
MAINTAINER apr
RUN /bin/bash -c 'source /home/condauser/anaconda3/bin/activate python2'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install jupyter -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install pandas -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install basemap -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin//conda install pyproj -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install fiona -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install gdal -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/pip install shapely'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/pip install geocoder'
