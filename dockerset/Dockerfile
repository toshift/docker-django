FROM centos:7

RUN yum update -y && \
    yum install -y epel-release && \
    yum install -y https://centos7.iuscommunity.org/ius-release.rpm && \
    yum install -y python35u python35u-pip python35u-devel && \
    yum clean all

RUN mkdir /code
WORKDIR /code

# celery 
ENV C_FORCE_ROOT true

RUN pyvenv-3.5 /tmp/python

# source /tmp/python/bin/activate
ENV VIRTUAL_ENV /tmp/python
ENV PATH $VIRTUAL_ENV/bin:$PATH

ADD . requirements.txt /code
RUN pip install -r requirements.txt
ADD . /code/
