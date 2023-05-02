FROM  jupyter/scipy-notebook:latest
LABEL maintainer="Motuzov <motuzov@gmail.com>"

USER root

RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    vim tree && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER ${NB_UID}

RUN  mamba install --name base black-jupyter pycodestyle -y && \
     mamba clean --all -f -y && \
     fix-permissions "${CONDA_DIR}" && \
     fix-permissions "/home/${NB_USER}"

RUN pip install black

COPY requirements.txt requirements.txt

RUN pip install -r requirements.txt

COPY setup.sh setup.sh

USER ${NB_UID}

WORKDIR "${HOME}"
