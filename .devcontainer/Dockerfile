# Use the Default Linux Universal dev container base image
FROM mcr.microsoft.com/devcontainers/universal:2

# Install system updates and required tools
USER root
RUN apt-get update && apt-get install -y curl python3 python3-pip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Node.js (LTS version) + npm
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
    && apt-get install -y nodejs \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Global Vue CLI installation
RUN npm install -g @vue/cli

# Install Flask
RUN pip install Flask

# Set working directory
WORKDIR /workspace

# Expose ports (Flask = 5000, Vue dev server = 5173)
EXPOSE 5000 5173

# Keep container running in VS Code
CMD ["sleep", "infinity"]

