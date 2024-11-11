FROM kubasejdak/node:22-24.04

# Settings.
ARG GO_VERSION=1.23.3
ARG HUGO_VERSION=0.138.0
ARG GO_URL=https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz
ARG HUGO_URL=https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb

# Install go.
RUN wget ${GO_URL} && \
    sudo  tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz && \
    rm go${GO_VERSION}.linux-amd64.tar.gz && \
    \
    # Install hugo.
    sudo apt update && \
    sudo apt install -y wget && \
    wget ${HUGO_URL} && \
    sudo apt install ./$(basename ${HUGO_URL}) && \
    rm $(basename ${HUGO_URL}) && \
    \
    # Install additional packages.
    sudo apt install -y curl && \
    \
    # Cleanup image.
    sudo apt remove -y wget && \
    sudo apt autoremove -y && \
    sudo apt clean && \
    sudo rm -rf /var/lib/apt/lists/*

ENV PATH=$PATH:/usr/local/go/bin
