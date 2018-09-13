BootStrap: docker
From: continuumio/miniconda3

%post

    export PATH=/opt/conda/bin:$PATH

    # make sure to have the latest conda version
    conda update -n base conda

    # add some extra channels
    conda config --add channels conda-forge
    conda config --add channels bioconda

    # install some bioinfo tools from Bioconda
    conda install --yes -c bioconda samtools==1.9
    conda install --yes -c bioconda bwa==0.7.17

%environment
    export PATH=/opt/conda/bin:$PATH
    export XDG_RUNTIME_DIR=""

%apprun samtools
    samtools "$@"

%apprun bwa
    bwa "$@"

