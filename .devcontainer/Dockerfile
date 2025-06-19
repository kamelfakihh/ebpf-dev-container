FROM ubuntu:24.04

ARG LLVM_VERSION="19"

# Define environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential wget curl git lsb-release software-properties-common gnupg
    
# Install llvm
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)" ${LLVM_VERSION}

# Set clang-{LLVM_VERSION} as default
RUN update-alternatives --install /usr/bin/clang clang /usr/bin/clang-${LLVM_VERSION} 100 && \
    update-alternatives --install /usr/bin/clang++ clang++ /usr/bin/clang++-${LLVM_VERSION} 100 && \
    update-alternatives --install /usr/bin/llvm-strip llvm-strip /usr/bin/llvm-strip-${LLVM_VERSION} 100

# Install eunomia-bpf development tools
RUN wget https://aka.pw/bpf-ecli -O /usr/bin/ecli && chmod +x /usr/bin/ecli && \
    wget https://github.com/eunomia-bpf/eunomia-bpf/releases/latest/download/ecc -O /usr/bin/ecc && chmod +x /usr/bin/ecc