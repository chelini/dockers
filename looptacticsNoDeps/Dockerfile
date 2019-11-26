# Docker file for loop tactics with no external deps except for pet and isl.

# Check http://releases.llvm.org/download.html#9.0.0 for the latest available binaries
FROM ubuntu:latest

RUN \
  apt-get update && \
  apt-get upgrade && \
  apt-get -y install git && \
  apt-get -y install cmake && \ 
  apt-get -y install build-essential && \
  apt-get -y install vim && \
  apt-get -y install libtool && \
  apt-get -y install libgmp3-dev && \
  apt-get -y install autoconf && \ 
  apt-get -y install libntl-dev && \
  apt-get -y install libxml2-dev && \
  apt-get -y install libtinfo-dev && \
  apt-get update 

# Make sure the image is updated, install some prerequisites,
# Download the latest version of Clang (official binary) for Ubuntu
# Extract the archive and add Clang to the PATH
RUN \
  apt-get install -y curl \
  && curl -SL http://releases.llvm.org/9.0.0/clang+llvm-9.0.0-x86_64-linux-gnu-ubuntu-18.04.tar.xz \
  | tar -xJC . && \
  mv clang+llvm-9.0.0-x86_64-linux-gnu-ubuntu-18.04 clang_9.0.0 && \
  echo 'export PATH=/clang_9.0.0/bin:$PATH' >> ~/.bashrc && \
  echo 'export LD_LIBRARY_PATH=/clang_9.0.0/lib:$LD_LIBRARY_PATH' >> ~/.bashrc


# Start from a Bash prompt
CMD [ "/bin/bash" ]
