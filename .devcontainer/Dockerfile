FROM ubuntu:22.04

# Define environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential wget curl lsb-release software-properties-common  
    
# Install llvm
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)"