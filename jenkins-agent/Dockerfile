# Use an appropriate base image
FROM jenkins/agent:bookworm-jdk17

USER root

RUN apt-get update --fix-missing && apt-get install -y \
    curl \
    coreutils \
    net-tools \
    procps \
    lsb-release \
    build-essential \
    wget \
    software-properties-common \
    python3 \
    python3-pip \
    python3-venv \
    && curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
       https://download.docker.com/linux/debian/gpg \
    && echo "deb [arch=$(dpkg --print-architecture) \
       signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
       https://download.docker.com/linux/debian \
       $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-get install -y docker-ce-cli \
    && rm -rf /var/lib/apt/lists/*