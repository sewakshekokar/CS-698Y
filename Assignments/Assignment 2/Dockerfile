# Simple Dockerfile for the student dropout fairness project
FROM python:3.11-slim

# Avoid interactive prompts
ENV DEBIAN_FRONTEND=noninteractive     PYTHONDONTWRITEBYTECODE=1     PYTHONUNBUFFERED=1

# System deps (optional; uncomment if you need build tools)
# RUN apt-get update && apt-get install -y --no-install-recommends \
#     build-essential \
#  && rm -rf /var/lib/apt/lists/*

# Create app directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r /app/requirements.txt

# (Optional) Jupyter for local notebook runs inside the container
RUN pip install --no-cache-dir jupyterlab

# Copy project files
COPY . /app

# Default command: open a shell.
CMD ["/bin/bash"]
