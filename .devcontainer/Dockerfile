ARG VARIANT=0-3.7-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}

ENV \
    DEBIAN_FRONTEND=noninteractive \
    PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

SHELL ["/bin/bash", "-ceux", "-o", "pipefail"]

RUN \
    pipx install poetry==1.2.0; \
    poetry completions bash >> ~/.bash_completion;

COPY .devcontainer/postcreate.sh /

RUN \
    chmod +x /postcreate.sh;
