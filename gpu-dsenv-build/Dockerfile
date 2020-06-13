# Bring the CUDAToolkit image
FROM nvidia/cuda:10.1-cudnn7-runtime-ubuntu18.04
# Update apt-get and install required packages
RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim
# Change working directory to /opt
WORKDIR /opt
# Install anaconda3 and delete used files
RUN wget https://repo.continuum.io/archive/Anaconda3-2019.10-Linux-x86_64.sh && \
    sh Anaconda3-2019.10-Linux-x86_64.sh -b -p/opt/Anaconda3 && \
    rm Anaconda3-2019.10-Linux-x86_64.sh
# pass python path
ENV PATH /opt/Anaconda3/bin:&PATH
# Upgrade pip and install required packages
RUN pip install --upgrade pip && pip install \
    keras==2.3 \
    # Version update due to anaconda3-2019.10
    scipy==1.4.1 \
    tensorflow-gpu==2.1
# Change workin dirctory to /
WORKDIR /
# Start jupyter lab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token==''"]