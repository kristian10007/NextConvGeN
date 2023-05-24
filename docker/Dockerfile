#FROM ubuntu:21.10
FROM nvidia/cuda:11.3.1-cudnn8-devel

RUN ln -s /usr/share/zoneinfo/Europe/Berlin /etc/localtime

# Fix missing NVIDIA keys for apt.
RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/3bf863cc.pub

RUN apt-get update \
    && apt-get install -y python3 pip wget \
    && apt-get dist-upgrade -y \
    && apt-get clean

RUN mkdir /benchmark
WORKDIR /benchmark

COPY requirements.txt /benchmark/requirements.txt
RUN pip install -r /benchmark/requirements.txt

WORKDIR /benchmark/data
CMD ["/usr/bin/python3", "run_all_exercises.py"]
