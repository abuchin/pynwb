#
# pynwb miniconda Dockerfile
#
# https://github.com/NeurodataWithoutBorders/pynwb
# http://pynwb.readthedocs.io/en/latest/index.html
#
# To run:
# - cd pynwb/docker/python36_test
# - docker build --tag neurodatawithoutborders/pynwb:python36_test -f ./Dockerfile ../..
# - docker run -it neurodatawithoutborders/pynwb:python36_test bash

# Pull base image.
FROM continuumio/miniconda3:latest

RUN apt-get update
USER root
SHELL ["/bin/bash", "-c"]

RUN conda update -y conda
RUN conda create -n python36 python=3.6
RUN source activate python36
COPY . /pynwb
WORKDIR /pynwb

RUN pip install -r 'requirements.txt'
RUN python setup.py build
RUN python setup.py install
