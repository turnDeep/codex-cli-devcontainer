# Use Node.js 20 as base image
FROM mcr.microsoft.com/devcontainers/javascript-node:1-20-bookworm

# Install additional dependencies
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    jq \
    python3 \
    python3-pip \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Switch to node user
USER node

# Set up workspace directory
WORKDIR /workspace

# Create necessary directories for Codex CLI
RUN mkdir -p /home/node/.codex \
    && mkdir -p /home/node/.codex/tmp \
    && mkdir -p /workspace/.codex

# Install Codex CLI globally
RUN npm install -g codex-cli

# Create a startup script
RUN echo '#!/bin/bash\n\
echo "🚀 Codex CLI Development Container Ready!"\n\
echo "Run \"codex\" to get started."\n\
' > /home/node/codex-setup.sh && chmod +x /home/node/codex-setup.sh

# Set shell to zsh
SHELL ["/bin/zsh", "-c"]

# Expose ports for OAuth callbacks
EXPOSE 3000 3002 5000 8080

# Set the entrypoint
ENTRYPOINT ["/bin/zsh"]
