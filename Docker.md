# Docker Notes


## Contents

- [Installation](https://docs.docker.com/engine/install/)
- [Basic Commands](#basic-commands)


## Basic Commands

```bash
# Display help information
docker --help

# Pull images from Docker registry
# NOTE: docker pull --help
docker pull <IMAGE:TAG>

# Push image to Docker registry
# NOTE: docker push --help
docker push <IMAGE:TAG>

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

# Remove dangling Docker images
docker rmi -f $(docker images -f "dangling=true" -q)

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

# Execute a command in a running Docker container
# NOTE: docker exec -it --help
# Example: docker exec -it <CONTAINER> /bin/sh
docker exec -it <CONTAINER> <COMMAND>

# Rebuild Docker Compose service
# NOTE: docker compose up --help
docker compose up -d --no-deps --build <SERVICE>

# Displays logs
# NOTE: docker logs --help
# Display docker logs
docker logs <CONTAINER_ID | CONTAINER_NAME>
# Follow docker logs
docker logs -f <CONTAINER_ID | CONTAINER_NAME>
# Follow docker logs with timestamp
docker logs -tf <CONTAINER_ID | CONTAINER_NAME>
```
