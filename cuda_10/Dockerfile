FROM nvidia/cuda:10.1-cudnn7-devel-ubuntu18.04
CMD nvidia-smi

RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         ca-certificates \
         libglib2.0-0 \
         libjpeg-dev \
         libpng-dev \
         python3 \
         python3-pip \
         python3-wheel \
         python3-setuptools \
         sqlite3 \
         libsqlite3-dev\
		 gcc gfortran libopenblas-dev liblapack-dev cython

COPY ./cuda_10/requirements.txt /opt/PatchSorter/requirements.txt
WORKDIR /opt/PatchSorter
RUN pip3 install -U pip
RUN pip3 install -r requirements.txt
COPY . /opt/PatchSorter

ADD . /opt/PatchSorter
CMD ["python3", "-m", "patchsorter"]
