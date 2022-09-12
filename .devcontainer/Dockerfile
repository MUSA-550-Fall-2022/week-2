FROM mambaorg/micromamba:0.25.1

ENV MAMBA_ROOT_PREFIX="/opt/conda"

COPY --chown=$MAMBA_USER:$MAMBA_USER environment.yml /tmp/environment.yml

RUN micromamba install -y -n base -f /tmp/environment.yml && \
    micromamba clean --all --yes 

USER root 

# Install some useful OS packages
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y --no-install-recommends --reinstall \

    # reinstall coreutils to get manpages for the standard commands (e.g. cp)
    coreutils \
    #
    # runs commands as superuser
    sudo \
    # pagination
    less \
    #
    #
    # version control
    git \
    #
    # Git Large File Storage
    git-lfs \
    #
    # simple text editor
    nano \
    #
    # less-simple text editor
    vim \
    #
    # compression
    zip \
    unzip \
    #
    # downloads files
    curl \
    wget
