FROM python:3.9-slim-bookworm

# Install necessary system packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl git gettext make python3-venv python3-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Create a new user
ARG USER=heatmap
RUN useradd -m ${USER} --shell /bin/bash --uid=1000

# Switch to the new user
USER ${USER}
ENV PATH="/home/${USER}/.local/bin:${PATH}"
# Upgrade pip and setuptools
RUN pip install --user -U pip setuptools build
