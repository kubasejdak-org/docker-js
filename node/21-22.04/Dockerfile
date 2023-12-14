FROM embeddedlinux/base:22.04

# Settings.
ARG NODE_VERSION=21
ARG NVMSH_VERSION=0.39.7

# Install node and latest npm.
RUN sudo rm /bin/sh && sudo ln -s /bin/bash /bin/sh && \
    sudo apt install -y wget && \
    sudo apt install --reinstall -y ca-certificates && \
    wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v${NVMSH_VERSION}/install.sh | bash && \
    export NVM_DIR="${HOME}/.nvm" && \
    . ${NVM_DIR}/nvm.sh && \
    nvm install ${NODE_VERSION} && \
    npm install -g npm@latest && \
    npm config -g set fund false && \
    \
    # Cleanup image.
    sudo apt remove -y wget && \
    sudo apt autoremove -y && \
    sudo apt clean && \
    sudo rm -rf /var/lib/apt/lists/*
