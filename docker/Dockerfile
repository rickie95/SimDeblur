FROM nvidia/cuda:11.7.0-runtime-ubuntu20.04

RUN apt-get update && apt-get install -y build-essential wget python3 python3-pip git && apt-get clean && rm -rf /var/lib/apt/lists/*


ENV CONDA_DIR /opt/conda
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh && \
     /bin/bash ~/miniconda.sh -b -p /opt/conda
     

# Put conda in path so we can use conda activate
ENV PATH=$CONDA_DIR/bin:$PATH

RUN git clone https://github.com/rickie95/SimDeblur

RUN conda init bash && \
    conda create -n simdeblur python=3.7

#RUN conda activate simdeblur && \ 
#    cd SimDeblur && \
#    chmod +x Install.sh && \
#    ./Install.sh

