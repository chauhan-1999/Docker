# 🐋 Docker Quick Reference Cheat Sheet

A comprehensive guide to Docker commands for building, managing, and orchestrating containers. 

---

## 📌 Table of Contents
* [🚀 Build Commands](#-build-commands)
* [🧹 Clean Up Commands](#-clean-up-commands)
* [💻 Container Interaction](#-container-interaction)
* [🔍 Container Inspection](#-container-inspection)
* [🖼️ Image Management](#️-image-management)
* [⚙️ Docker Run Flags](#️-docker-run-flags)
* [🔑 Registry Commands](#-registry-commands)
* [🌐 Network & Volumes](#-network--volumes)
* [🐝 Docker Swarm & Services](#-docker-swarm--services)
* [📁 Filesystem & Environment](#-filesystem--environment)
* [🐙 Docker Compose](#-docker-compose)
* [📊 Health & Stats](#-health--stats)
* [📚 External Resources](#-external-resources)

---

## 🚀 Build Commands
Used to create images from a `Dockerfile`.



| Command | Description |
| :--- | :--- |
| `docker build -t <image_name> .` | Build an image from a Dockerfile in the current directory and tag it. |
| `docker build --no-cache -t <image_name> .` | Build image without using the cache. |
| `docker build -f <file_name> -t <image_name> .` | Build image using a specified Dockerfile. |

---

## 🧹 Clean Up Commands
Keep your system lean by removing unused resources.

* `docker system prune`: Remove all unused Docker resources (containers, images, networks, volumes).
* `docker container prune`: Remove all stopped containers.
* `docker image prune`: Remove unused images.
* `docker volume prune`: Remove unused volumes.
* `docker network prune`: Remove unused networks.

---

## 💻 Container Interaction
Manage the lifecycle of your containers.

* `docker run <image_name>`: Run a Docker image as a container.
* `docker start <container_id>`: Start a stopped container.
* `docker stop <container_id>`: Stop a running container.
* `docker restart <container_id>`: Restart a running container.
* `docker exec -it <container_id> <command>`: Execute a command inside a running container interactively.

---

## 🔍 Container Inspection
Monitor and debug container status.

* `docker ps`: List running containers.
* `docker ps -a`: List all containers, including stopped ones.
* `docker logs <container_id>`: Fetch the logs of a specific container.
* `docker inspect <container_id>`: Inspect detailed information about a container.

---

## 🖼️ Image Management
Handle images locally and interact with registries.

* `docker images`: List available Docker images.
* `docker pull <image_name>`: Pull a Docker image from a registry.
* `docker push <image_name>`: Push a Docker image to a registry.
* `docker rmi <image_id>`: Remove a Docker image.

---

## ⚙️ Docker Run Flags
Common options used with the `docker run` command.

* `docker run -d <image_name>`: Run in detached mode (background).
* `docker run -p <host_port>:<container_port> <image_name>`: Publish container ports to the host.
* `docker run -v <host_path>:<container_path> <image_name>`: Mount a host directory or volume.
* `docker run --name <container_name> <image_name>`: Assign a custom name to the container.

---

## 🔑 Registry Commands
Manage your connection to Docker Hub or private registries.

* `docker login`: Log in to a Docker registry.
* `docker logout`: Log out from a Docker registry.
* `docker search <term>`: Search for Docker images in a registry.
* `docker pull <registry>/<image_name>`: Pull from a specific registry.

---

## 🌐 Network & Volumes
Persistence and communication settings.



### Networks
* `docker network create <network_name>`: Create a Docker network.
* `docker network ls`: List available Docker networks.
* `docker network inspect <network_name>`: View detailed network info.
* `docker network connect <network_name> <container_name>`: Connect a container to a network.

### Volumes
* `docker volume create <volume_name>`: Create a Docker volume.
* `docker volume ls`: List available Docker volumes.
* `docker volume inspect <volume_name>`: View detailed volume info.
* `docker volume rm <volume_name>`: Remove a Docker volume.

---

## 🐝 Docker Swarm & Services
Commands for orchestration and scaling.

* `docker swarm init`: Initialize a swarm on the current node.
* `docker swarm join`: Join a swarm as a worker node.
* `docker node ls`: List nodes in the swarm.
* `docker service create --name <name> <image>`: Create a service.
* `docker service ls`: List running services.
* `docker service scale <name>=<replicas>`: Scale service replicas.
* `docker service logs <name>`: View service logs.

---

## 📁 Filesystem & Environment
Managing data and variables.

* `docker cp <container_id>:<path> <host_path>`: Copy files from container to host.
* `docker cp <host_path> <container_id>:<path>`: Copy files from host to container.
* `docker run -e <VAR>=<VALUE> <image>`: Set environment variables.

---

## 🐙 Docker Compose
Manage multi-container applications easily.

```bash
docker-compose up      # Create and start containers
docker-compose down    # Stop and remove containers
docker-compose ps      # List containers
```

## 📊 Health & Stats
Monitor and manage the health and performance of your containers in real-time.



* **HEALTHCHECK instruction**: Define a command in your `Dockerfile` to let Docker know how to check if the container is still "healthy."
* `docker container inspect --format='{{json .State.Health}}' <container_name>`: Retrieve the detailed health status of a specific container in JSON format.
* `docker stats`: Display a live, continuous stream of resource usage statistics (CPU, Memory, Network I/O) for all running containers.
* `docker stats <container_name>`: Display the live resource usage for a specific container by name or ID.

---

## 📚 External Resources
For more in-depth learning, advanced configurations, and the latest updates, check out these curated resources:

* **[Coursera Docker Cheat Sheet Collection](https://www.coursera.org/collections/docker-cheat-sheet)**: A professional collection of guides and visual cheat sheets for mastering Docker.
* **[Official Docker Documentation](https://docs.docker.com/)**: The primary source for all Docker features and installation guides.

---

> [!TIP]
> Use `docker stats --no-stream` if you want a single snapshot of resource usage rather than a live feed.
docker-compose logs    # View logs

