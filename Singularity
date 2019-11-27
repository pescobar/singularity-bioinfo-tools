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
    # to force the app version use appname==1.1.1
    conda install --yes -c bioconda samtools
    conda install --yes -c bioconda fastqc
    conda install --yes -c bioconda trimmomatic
    conda install --yes -c bioconda rseqc
    conda install --yes -c bioconda star
    conda install --yes -c bioconda salmon
    conda install --yes -c bioconda kallisto
    conda install --yes -c bioconda htseq
    conda install --yes -c bioconda sra-tools
    conda install --yes -c bioconda subread
    conda install --yes -c bioconda multiqc
    conda install --yes -c bioconda bedtools
    conda install --yes -c bioconda gffread

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

%apprun bedtools
    bedtools "@"

%apprun gffread
    gffread "@"
