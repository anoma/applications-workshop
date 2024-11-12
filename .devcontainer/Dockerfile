# OS
ARG VARIANT="ubuntu-22.04"

FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -y install --no-install-recommends \
    curl \
    sudo \
    wget \
    git \
    && apt-get clean

ENV PATH=${PATH}:/home/vscode/.local/bin
RUN sudo bash -c 'mkdir -p /home/vscode/.local/bin'
RUN sudo bash -c "chown -R vscode /home/vscode/.local/"
RUN sudo bash -c 'chmod -R a+rXw /home/vscode/.local'

# to be used by the juvix extension
RUN sudo bash -c 'mkdir -p /home/vscode/.local/juvix'

RUN sudo bash -c 'curl -s https://api.github.com/repos/anoma/juvix/releases/tags/v0.6.8 \
       | grep -a "browser_download_url.*linux" \
       | cut -d : -f 2,3 \
       | tr -d \" \
       | head -n 1 \
       | wget --output-document juvix.tar.gz -qi - \
      && tar xfv juvix.tar.gz --directory=/home/vscode/.local/bin/'
