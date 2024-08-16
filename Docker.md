# Docker Notes

> [!NOTE]
> Learn more at [Docker Docs](https://docs.docker.com/engine/install/).

## Contents

- [Installation](#installation)
  - [Install Docker on Fedora](#install-docker-on-fedora)
  - [Install Docker on Ubuntu](#install-docker-on-ubuntu)
- [Basic Commands](#basic-commands)

## Installation

### Install Docker on Fedora

```bash
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo

sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker

sudo systemctl enable docker.service
sudo systemctl enable containerd.service

systemctl reboot

docker run hello-world
```


### Install Docker on Ubuntu

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker

systemctl reboot

docker run hello-world
```


## Basic Commands

```bash
# Display help information
docker --help

# Pull images from Docker registry
# NOTE: pull --help
docker pull <IMAGE:TAG>

# Display images
# NOTE: docker images --help
docker images

# Display running containers
# NOTE: docker ps --help
docker ps

# Display all containers
docker ps -a

# Display volumes
# NOTE: docker volume --help
docker volume ls

# Stop container
# NOTE: docker stop --help
docker stop <CONTAINER>

# Remove container
# NOTE: docker rm --help
docker rm <CONTAINER>

# Remove image
# NOTE: docker rmi --help
docker rmi <IMAGE>

# Remove all unused volume
# NOTE: docker volume prune --help
docker volume prune --all

# Remove all unused data
# NOTE: docker system prune --help
docker system prune --all

# Display Docker disk usage
# NOTE: docker system df --help
docker system df

# Get Docker container IP address
# NOTE: docker inspect --help
docker inspect <CONTAINER> | grep "IPAddress"

# Remove dangling Docker images
docker rmi -f $(docker images -f "dangling=true" -q)
```
