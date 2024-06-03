# Use an official Ubuntu as a parent image
FROM ubuntu:latest

# Set environment variables to avoid prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Install Ansible and other necessary packages
# IMPORTANT: may require 'apt-get install sshpass' 
RUN apt update && apt install -y \
    ansible \
    openssh-client \
    openssh-server \
    sudo \
    vim \
    nano

# Create and switch to a non-root user
RUN useradd -m -s /bin/bash ansibleuser && \
    echo 'ansibleuser:password' | chpasswd && \
    adduser ansibleuser sudo

# Set the working directory
WORKDIR /home/ansibleuser

# Run the container as the new user
USER ansibleuser
