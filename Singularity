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
    conda install --yes -c bioconda fastqc==0.11.8
    conda install --yes -c bioconda trimmomatic==0.38
    conda install --yes -c bioconda rseqc==2.6.4
    conda install --yes -c bioconda star==2.6.1b
    conda install --yes -c bioconda salmon==0.11.3
    conda install --yes -c bioconda kallisto==0.44.0
    conda install --yes -c bioconda htseq==0.9.1
    conda install --yes -c bioconda sra-tools==2.9.1_1
    conda install --yes -c bioconda subread==1.6.2
    conda install --yes -c bioconda multiqc==1.6a0

%environment
    export PATH=/opt/conda/bin:$PATH
    export XDG_RUNTIME_DIR=""

%apprun samtools
    samtools "$@"

%apprun fastqc
    fastqc "$@"

%apprun trimmomatic
    trimmomatic "@"

%apprun STAR
    START "@"

%apprun STARlong
    STARTlong "@"

%apprun salmon
    salmon "@"

%apprun kallisto
    kallisto "@"

%apprun htseq-count
    htseq-count "@"

%apprun htseq-qa
    htseq-qa "@"

%apprun sra-sort
    sra-sort "@"

%apprun sra-stat
    sra-stat "@"

%apprun multiqc
    multiqc "@"
