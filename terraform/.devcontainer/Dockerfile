FROM debian:bookworm-slim

# Install required packages for neovim

RUN apt-get update && apt-get install -y \
    neovim \
    python3 \
    python3-pip \
    jq \
    curl \
    git \
    npm \
    gpg \
    wget \
    lsb-release
    
RUN wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" >> /etc/apt/sources.list.d/hashicorp.list

RUN apt-get update && apt-get install terraform

RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash
