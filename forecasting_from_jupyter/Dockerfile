FROM  jupyter/scipy-notebook:latest
LABEL maintainer="Motuzov <motuzov@gmail.com>"

USER root

RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    vim && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER ${NB_UID}
# Install Python 3 packages
RUN pip install torch torchvision pyarrow pytorch-lightning optuna pytorch-forecasting && \
    pip install -U pytest 

RUN  mamba install --name base pycodestyle -y && \
     mamba clean --all -f -y && \
     fix-permissions "${CONDA_DIR}" && \
     fix-permissions "/home/${NB_USER}"

USER ${NB_UID}

WORKDIR "${HOME}"
