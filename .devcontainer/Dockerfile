FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install required tools
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    && rm -rf /var/lib/apt/lists/*

# Set environment variable
ENV FLUTTER_VERSION=3.22.1
ENV PATH="/root/flutter/bin:/root/flutter/bin/cache/dart-sdk/bin:${PATH}"

# Install Flutter
RUN git clone https://github.com/flutter/flutter.git /root/flutter \
    && flutter channel stable \
    && flutter upgrade \
    && flutter precache

# Accept Android licenses (optional)
RUN yes | flutter doctor --android-licenses || true

# Run flutter doctor
RUN flutter doctor
