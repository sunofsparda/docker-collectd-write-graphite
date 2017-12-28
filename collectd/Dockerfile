FROM ubuntu:16.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt -y update
RUN apt -y install collectd curl python-pip

# add a fake mtab for host disk stats
ADD etc_mtab /etc/mtab

ADD collectd.conf.tpl /etc/collectd/collectd.conf.tpl

RUN pip install envtpl
ADD start_container /usr/bin/start_container
RUN chmod +x /usr/bin/start_container
CMD start_container
