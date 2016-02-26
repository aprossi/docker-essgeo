FROM ubuntu:latest
MAINTAINER apr

# from https://github.com/timlinux/docker-qgis-desktop/blob/master/Dockerfile
RUN echo "deb http://ppa.launchpad.net/ubuntugis/ubuntugis-unstable/ubuntu trusty main" >> /etc/apt/sources.list
RUN gpg --keyserver keyserver.ubuntu.com --recv 314DF160
RUN gpg --export --armor 314DF160 | sudo apt-key add -


RUN apt-get update -y

RUN apt-get install qgis -y