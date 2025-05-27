# See here for image contents: https://github.com/microsoft/vscode-dev-containers

FROM mcr.microsoft.com/vscode/devcontainers/go

RUN apt update && \
    apt-get install -y automake libtool make gcc pkg-config wget

RUN mkdir -p /tmp/yara-build && \
    cd /tmp/yara-build && \
    wget -O yara-4.4.0.tar.gz https://github.com/VirusTotal/yara/archive/refs/tags/v4.4.0.tar.gz && \
    tar -zxf yara-4.4.0.tar.gz && \
    cd yara-4.4.0 && \
    ./bootstrap.sh && \
    ./configure && \
    make && \
    make install && \
    cd / && \
    rm -rf /tmp/yara-build