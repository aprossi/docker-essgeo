# from https://github.com/rothnic/anaconda-notebook
# see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
# TAKEN FROM FROM rothnic/anaconda-notebook
MAINTAINER apr
######################################
FROM ubuntu:latest
# MAINTAINER Nick Roth "nlr06886@gmail.com"
MAINTAINER apr


# Link in our build files to the docker image
ADD src/ /tmp

# Run all ubuntu updates and apt-get installs
RUN export DEBIAN_FRONTEND=noninteractive && \
	apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y git \
		wget \
		bzip2 \
		build-essential \
		python-dev \
		gfortran \
	&& apt-get clean

# Create conda user, get anaconda by web or locally
RUN useradd --create-home --home-dir /home/condauser --shell /bin/bash condauser
RUN /tmp/get_anaconda.sh

# Run all python installs
# Perform any cleanup of the install as needed
USER condauser
RUN /tmp/install.sh

# Copy notebook config into ipython directory
# Make sure our user owns the directory
USER root
RUN  apt-get --purge -y autoremove wget && \
	cp /tmp/ipython_notebook_config.py /home/condauser/.ipython/profile_default/ && \
	cp /tmp/matplotlib_nb_init.py /home/condauser/.ipython/profile_default/startup && \
	chown condauser:condauser /home/condauser -R

# Set persistent environment variables for python3 and python2
ENV PY2PATH=/home/condauser/anaconda3/envs/python2/bin
ENV PY3PATH=/home/condauser/anaconda3/bin

# Install the python2 ipython kernel
RUN $PY2PATH/python $PY2PATH/ipython kernelspec install-self

# Setup our environment for running the ipython notebook
# Setting user here makes sure ipython notebook is run as user, not root
EXPOSE 8888
USER condauser
ENV HOME=/home/condauser
ENV SHELL=/bin/bash
ENV USER=condauser
WORKDIR /home/condauser/notebooks

CMD $PY3PATH/ipython notebook

######################################

# # install gdal
USER root
RUN echo "deb http://ppa.launchpad.net/ubuntugis/ubuntugis-unstable/ubuntu trusty main" >> /etc/apt/sources.list
RUN gpg --keyserver keyserver.ubuntu.com --recv 314DF160
RUN gpg --export --armor 314DF160 | apt-key add -
RUN apt-get update -y
# RUN apt-get install libgdal-dev libgdal1-dev  -y
RUN apt-get install libgdal1h -y

# # install the rest for jupyter
USER condauser
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
