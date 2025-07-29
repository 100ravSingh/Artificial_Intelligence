FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install basic tools
RUN apt-get update && apt-get install -y curl git wget build-essential

# Install Miniconda
ENV CONDA_DIR=/opt/conda
ENV PATH=$CONDA_DIR/bin:$PATH
RUN curl -fsSL https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o miniconda.sh && \
    bash miniconda.sh -b -p $CONDA_DIR && \
    rm miniconda.sh && \
    conda clean -afy

# Create a default environment and install Jupyter
RUN conda create -n dev python=3.11 -y && \
    echo "conda activate dev" >> ~/.bashrc && \
    /bin/bash -c "source ~/.bashrc && conda activate dev && conda install -y notebook jupyterlab pandas numpy matplotlib scikit-learn"

# Expose Jupyter port
EXPOSE 8888
