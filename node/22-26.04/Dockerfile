FROM kubasejdak/base:26.04

# Settings.
ARG NODE_VERSION=22
ARG NVMSH_VERSION=0.40.4

# Install node and npm.
RUN wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v${NVMSH_VERSION}/install.sh | bash && \
    export NVM_DIR="${HOME}/.nvm" && \
    . ${NVM_DIR}/nvm.sh && \
    nvm install ${NODE_VERSION} && \
    npm install -g npm@11.11.0 && \
    npm config -g set fund false && \
    \
    # Cleanup image.
    sudo apt autoremove -y && \
    sudo apt clean && \
    sudo rm -rf /var/lib/apt/lists/*
