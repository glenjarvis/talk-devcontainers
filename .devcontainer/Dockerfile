# Deno + Slidev dev container
FROM mcr.microsoft.com/devcontainers/base:jammy

# Install dependencies and Deno
USER root
RUN apt-get update && apt-get install -y --no-install-recommends \
   curl ca-certificates git unzip bash tini \
   && rm -rf /var/lib/apt/lists/*

# Switch to vscode before installing Deno to keep everything user-owned
USER vscode
ENV DENO_INSTALL=/home/vscode/.deno
ENV PATH="$DENO_INSTALL/bin:$PATH"

RUN curl -fsSL https://deno.land/install.sh | sh && deno --version

# Install Slidev globally for the user; lockfile lives in a writable place
ENV DENO_INSTALL_ROOT=/home/vscode/.deno/bin
RUN deno install -g -A npm:@slidev/cli && slidev --version || true

EXPOSE 3030

SHELL ["/bin/bash", "-c"]

