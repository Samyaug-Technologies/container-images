# ------------------------------------------------------------
# Generic Ubuntu-based Python 3.11 base image
# Suitable for internal Quay registry use
# ------------------------------------------------------------
FROM ubuntu:22.04

LABEL maintainer="you@your-org.com"
LABEL description="Ubuntu 22.04 + Python 3.11 base image"
LABEL org.opencontainers.image.source="https://github.com/your-org/ubuntu-python3.11"

ENV DEBIAN_FRONTEND=noninteractive \
    PYTHONUNBUFFERED=1 \
    LANG=C.UTF-8 \
    LC_ALL=C.UTF-8 \
    PATH="/usr/local/bin:$PATH"

# Install Python 3.11 and core tooling
RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    software-properties-common curl build-essential ca-certificates gnupg \
 && add-apt-repository ppa:deadsnakes/ppa -y \
 && apt-get update \
 && apt-get install -y --no-install-recommends \
    python3.11 python3.11-venv python3.11-distutils python3.11-dev python3-pip \
 && ln -sf /usr/bin/python3.11 /usr/bin/python3 \
 && python3 -m pip install --no-cache-dir --upgrade pip setuptools wheel \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Default Python symlinks
RUN ln -sf /usr/bin/python3 /usr/bin/python && ln -sf /usr/bin/pip3 /usr/bin/pip

# Verify installation
RUN python3 --version && pip --version

# Default working directory (can be overridden by downstream images)
WORKDIR /workspace

# Default command — show Python version
CMD ["python3", "--version"]
