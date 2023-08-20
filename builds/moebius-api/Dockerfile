FROM ubuntu:22.04

# Set the timezone to UTC
RUN ln -sf /usr/share/zoneinfo/Etc/UTC /etc/localtime

# Set non-interactive mode during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package information and install necessary packages
RUN apt-get update && apt-get install -y \
    wget \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Download and install Go 1.21
RUN wget https://go.dev/dl/go1.21.0.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.21.0.linux-amd64.tar.gz && \
    rm go1.21.0.linux-amd64.tar.gz

# Set Go environment variables
ENV PATH="/usr/local/go/bin:${PATH}"
ENV GOPATH="/go"
ENV GOBIN="/go/bin"

# Create the working directory if it doesn't exist
RUN mkdir -p /moebius-api

# Set the working directory
WORKDIR /moebius-api

# Display Go version
RUN go version

# Force the container to be active
CMD ["tail", "-f", "/dev/null"]




