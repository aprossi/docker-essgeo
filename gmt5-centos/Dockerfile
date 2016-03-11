FROM centos:latest
ENV export PATH=$PATH
MAINTAINER apr

RUN yum update -y
RUN yum install -y wget
RUN wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -Uvh epel-release-latest-7.noarch.rpm
RUN rm epel-release-latest-7.noarch.rpm
RUN yum install nano -y
RUN yum install ssh -y
RUN yum install -y GMT gshhg-gmt-nc4 gshhg-gmt-nc4-high dcw-gmt
RUN yum install -y gmt-doc
RUN yum install -y gshhg-gmt-nc4-full
RUN yum install -y ghostscript



