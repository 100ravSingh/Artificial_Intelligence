FROM mcr.microsoft.com/devcontainers/base:ubuntu

RUN apt-get update && apt-get install -y curl git wget build-essential

ENV CONDA_DIR=/opt/conda
ENV PATH=$CONDA_DIR/bin:$PATH
RUN curl -fsSL https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o miniconda.sh && \
    bash miniconda.sh -b -p $CONDA_DIR && \
    rm miniconda.sh && \
    conda clean -afy

SHELL ["/bin/bash", "-c"]
RUN conda config --set always_yes yes && \
    conda config --set channel_priority strict && \
    conda tos accept --channel https://repo.anaconda.com/pkgs/main && \
    conda tos accept --channel https://repo.anaconda.com/pkgs/r && \
    conda init bash

COPY requirements.txt /tmp/requirements.txt
RUN conda create -n dev python=3.11 jupyter jupyterlab -y && \
    conda run -n dev pip install -r /tmp/requirements.txt && \
    echo "conda activate dev" >> /root/.bashrc
