FROM kubasejdak/base:24.04

# Settings.
ARG NODE_VERSION=22
ARG NVMSH_VERSION=0.39.7

# Install node and latest npm.
RUN sudo apt update && \
    sudo apt install -y wget && \
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
