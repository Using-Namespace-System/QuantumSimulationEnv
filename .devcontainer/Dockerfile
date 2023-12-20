FROM docker.io/nvidia/cuda:12.3.1-runtime-ubuntu22.04

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Configure
RUN apt-get -y update \
    # install git
    && apt-get -y install git openssh-client less iproute2 procps lsb-release \
    # Create user
    && groupadd --gid $USER_GID $USERNAME \
    && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
    #&&sudo -H -u vscode bash -c 'echo "I am $USER, with uid $UID"' \
    # Clean up
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*