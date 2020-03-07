FROM continuumio/miniconda3

# Install procps so that Nextflow can poll CPU usage
RUN apt-get update && apt-get install -y procps && apt-get clean -y \
    && apt-get -qqy install \
                    libboost-all-dev \
                    g++ \
                    vim \
		    emacs24\
    && rm -rf /var/lib/apt/lists/*
RUN conda install -c conda-forge boost-cpp && \
    conda install -c bioconda samtools && \
    conda install -c conda-forge numpy && \
    conda install -c conda-forge pandas && \
    conda install -c conda-forge matplotlib

RUN git clone https://github.com/adeslatt/wgbs_tools.git wgbs_tools
WORKDIR /wgbs_tools
RUN python3 setup.py

#ADD ../../wgbs_tools/bam2pat.py /usr/local/bin/
#RUN chmod +x /usr/local/bin/bam2pat.py

