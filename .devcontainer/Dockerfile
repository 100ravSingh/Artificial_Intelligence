FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install system dependencies
RUN apt-get update && apt-get install -y curl git wget build-essential

# Install Miniconda
ENV CONDA_DIR=/opt/conda
ENV PATH=$CONDA_DIR/bin:$PATH
RUN curl -fsSL https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o miniconda.sh && \
    bash miniconda.sh -b -p $CONDA_DIR && \
    rm miniconda.sh && \
    conda clean -afy

# Accept ToS and initialize conda shell
SHELL ["/bin/bash", "-c"]
RUN conda config --set always_yes yes && \
    conda config --set channel_priority strict && \
    conda tos accept --channel https://repo.anaconda.com/pkgs/main && \
    conda tos accept --channel https://repo.anaconda.com/pkgs/r && \
    conda init bash

# Copy requirements.txt and install packages in a named environment
COPY requirements.txt /tmp/requirements.txt
RUN source ~/.bashrc && \
    conda create -n dev python=3.11 -y && \
    echo "conda activate dev" >> ~/.bashrc && \
    source ~/.bashrc && \
    conda activate dev && \
    pip install -r /tmp/requirements.txt
