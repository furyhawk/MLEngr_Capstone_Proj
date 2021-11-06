# Build an image that can do training and inference in SageMaker
# This is a Python 3 image that uses the nginx, gunicorn, flask stack
# for serving inferences in a stable way.

FROM ubuntu:18.04

MAINTAINER Amazon AI <sage-learner@amazon.com>


RUN apt-get -y update && apt-get install -y --no-install-recommends \
    wget \
    python3-pip \
    python3-setuptools \
    nginx \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update
RUN apt-get install -y python3-dev  
RUN apt-get install -y build-essential

RUN ln -s /usr/bin/python3 /usr/bin/python
RUN ln -s /usr/bin/pip3 /usr/bin/pip

# Here we get all python packages.
# pip leaves the install caches populated which uses
# a significant amount of space. These optimizations save a fair amount of space in the
# image, which reduces start up time.
RUN python -m pip install --upgrade pip
RUN pip --no-cache-dir install Cython
RUN pip --no-cache-dir install numpy 
RUN pip --no-cache-dir install pandas
RUN pip --no-cache-dir install scikit-learn
RUN pip --no-cache-dir install sentence-transformers
RUN pip --no-cache-dir install hdbscan
# RUN pip --no-cache-dir install matplotlib
# RUN pip --no-cache-dir install seaborn
RUN pip --no-cache-dir install loglizer
RUN pip --no-cache-dir install flask gunicorn

RUN pip list


# Set some environment variables. PYTHONUNBUFFERED keeps Python from buffering our standard
# output stream, which means that logs can be delivered to the user quickly. PYTHONDONTWRITEBYTECODE
# keeps Python from writing the .pyc files which are unnecessary in this case. We also update
# PATH so that the train and serve programs are found when the container is invoked.

ENV PYTHONUNBUFFERED=TRUE
ENV PYTHONDONTWRITEBYTECODE=TRUE
ENV PATH="/opt/program:${PATH}"

# Set up the program in the image
COPY hdbscan-cluster /opt/program
WORKDIR /opt/program

