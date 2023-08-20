FROM ubuntu:22.04

# Set the timezone to UTC
RUN ln -sf /usr/share/zoneinfo/Etc/UTC /etc/localtime

# Set non-interactive mode during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package information and install necessary packages
RUN apt-get update && \
    apt-get install -y \
        curl && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt-get install -y nodejs && \
    apt-get purge -y curl && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Create the working directory if it doesn't exist
RUN mkdir -p /moebius

# Set the working directory
WORKDIR /moebius

# Display Node.js and npm versions
RUN node -v && npm -v

# Force the container to be active
CMD ["tail", "-f", "/dev/null"]