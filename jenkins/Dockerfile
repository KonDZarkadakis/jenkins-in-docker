# image
FROM jenkins/jenkins:2.473-jdk17


# Switch to root user to install dependencies
USER root


# Install dependencies
RUN apt-get update && apt-get install -y \
    lsb-release \
    python3-pip \
    curl \
    && curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
       https://download.docker.com/linux/debian/gpg \
    && echo "deb [arch=$(dpkg --print-architecture) \
       signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
       https://download.docker.com/linux/debian \
       $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-get install -y docker-ce-cli \
    && rm -rf /var/lib/apt/lists/*


# Switch back to Jenkins user to install jenkins plugin
USER jenkins