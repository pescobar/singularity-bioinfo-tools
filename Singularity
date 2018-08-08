BootStrap: docker
From: ubuntu:16.04

%post

    # install some system deps
    apt-get -y update
    apt-get -y install locales curl bzip2 less unzip
    # some extra devel libs
    apt-get -y install zlib1g-dev libssl-dev
    locale-gen en_US.UTF-8
    apt-get clean

    # download and install miniconda3
    curl -sSL -O https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh -p /opt/miniconda3 -b
    rm -fr Miniconda3-latest-Linux-x86_64.sh
    export PATH=/opt/miniconda3/bin:$PATH
    conda update -n base conda
    conda config --add channels conda-forge
    conda config --add channels bioconda

    # install some bioinfo tools from Bioconda
    conda install --yes -c bioconda samtools==1.9
    conda install --yes -c bioconda bwa==0.7.17


%environment
    export LANG=en_US.UTF-8
    export LANGUAGE=en_US:en
    export LC_ALL=en_US.UTF-8
    export PATH=/opt/miniconda3/bin:$PATH
    export XDG_RUNTIME_DIR=""

%apprun samtools
    samtools "$@"

%apprun bwa
    bwa "$@"

