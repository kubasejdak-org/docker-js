FROM kubasejdak/node:20-24.04

# Settings.
ARG HUGO_VERSION=0.129.0
ARG HUGO_URL=https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb

# Install node and latest npm.
RUN sudo apt install -y wget && \
    wget ${HUGO_URL} && \
    sudo apt install ./$(basename ${HUGO_URL}) && \
    rm $(basename ${HUGO_URL}) && \
    \
    # Cleanup image.
    sudo apt remove -y wget && \
    sudo apt autoremove -y && \
    sudo apt clean && \
    sudo rm -rf /var/lib/apt/lists/*
