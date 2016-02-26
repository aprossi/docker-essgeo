# from https://github.com/rothnic/anaconda-notebook
# see https://github.com/rothnic/anaconda-notebook/blob/master/Dockerfile
FROM rothnic/anaconda-notebook
MAINTAINER apr
RUN /bin/bash -c 'source /home/condauser/anaconda3/bin/activate python2'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install jupyter -y'
RUN /bin/bash -c '/home/condauser/anaconda3/bin/conda install pandas -y'

