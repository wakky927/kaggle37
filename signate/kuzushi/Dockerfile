FROM nvidia/cuda:10.2-cudnn7-runtime-ubuntu18.04

# update & install the minimum required libraries
RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim \
    git

# install conda
WORKDIR /opt
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    sh Miniconda3-latest-Linux-x86_64.sh -b -p /opt/miniconda3 && \
    rm -r Miniconda3-latest-Linux-x86_64.sh

ENV PATH /opt/miniconda3/bin:$PATH

# setting environment
COPY venv.yaml .

RUN pip install --upgrade pip && \
    conda update -n base -c defaults conda && \
    conda env create -f venv.yaml && \
    conda init && \
    echo "conda activate venv" >> ~/.bashrc

ENV CONDA_DEFAULT_ENV venv && \
    PATH /opt/conda/envs/venv/bin:$PATH

# move modules directory
WORKDIR /

# git clone
RUN git clone https://github.com/wakky927/kuzushi.git

# move modules directory
WORKDIR /kuzushi/

CMD ["/bin/bash"]