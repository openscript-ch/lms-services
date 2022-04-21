# lms-services

This repository contains the configuration of our learning management system (lms) setup.

## Set up

Before the lms service can be deployed, a host needs to be set up.

### Environment

These steps describe how to set up the system environment on Ubuntu 20.04 LTS on ARM or x86_64:

1. Install updates <br> `apt update && apt upgrade`
1. Install Docker dependencies <br> `apt install apt-transport-https ca-certificates curl gnupg lsb-release`
1. Import Dockers GPG key <br> `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`
1. Add Dockers apt repository 
   - On x86_64 <br> `echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null`
   - On ARM <br> `echo "deb [arch=arm64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null`
1. Install Docker <br> `apt update && apt install docker-ce docker-ce-cli containerd.io`
1. Create directory for Docker cli plugins <br> `mkdir -p /usr/local/lib/docker/cli-plugins`
1. Download `docker-compose` executable
   - On x86_64 <br> `curl -SL https://github.com/docker/compose/releases/download/v2.4.1/docker-compose-linux-x86_64 -o /usr/local/lib/docker/cli-plugins/docker-compose`
   - On ARM <br> `curl -SL https://github.com/docker/compose/releases/download/v2.4.1/docker-compose-linux-aarch64 -o /usr/local/lib/docker/cli-plugins/docker-compose`
1. Give executable permission to Docker Compose <br> `chmod +x /usr/local/lib/docker/cli-plugins/docker-compose`
1. Validate the installation of Docker (>= 20.10.14) <br> `docker -v`
1. Validate the installation of Docker Compose (>= 2.4.1) <br> `docker-compose -v`

The following sources were used:

- [Documentation: Docker](https://docs.docker.com/engine/install/ubuntu/)
- [Documentation: Docker Compose V2](https://docs.docker.com/compose/cli-command/#installing-compose-v2)

### Application system

### Deployment user