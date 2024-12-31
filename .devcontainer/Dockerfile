FROM quay.io/jupyter/scipy-notebook:latest

# Move requiremnts.txt to work directory
COPY --chown=${NB_UID}:${NB_GID} ./requirements.txt ${HOME}/work/requirements.txt

# Install requirements
RUN pip install -r ${HOME}/work/requirements.txt && \
    pip cache purge

# Install conda packages
RUN fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"


WORKDIR "${HOME}"