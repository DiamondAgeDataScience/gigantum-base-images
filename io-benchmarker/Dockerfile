FROM gigdev/gm-quickstart
MAINTAINER Gigantum <hello@gigantum.io>

# We assume we just built the base image, so system is up-to-date
RUN apt-get -y install phoronix-test-suite fio iozone3

# This will likely pull in some dependencies
RUN pip3 install nibabel==2.2.1

CMD ["true"]

