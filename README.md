# IS436-Classwork-Foosball
IS436 Classwork Foosball Project



# 🐳 Docker Command Reference

A comprehensive guide and quick reference for essential Docker commands — covering Images, Containers, Volumes, and Networks.

---

## 📘 Quick Command Cheat Sheet

| Category | Description | Command |
|-----------|--------------|----------|
| 🧱 Images | List all local images | `docker images` |
|  | Delete an image | `docker rmi <image_name>` |
|  | Remove unused images | `docker image prune` |
|  | Build image from Dockerfile | `docker build -t <image_name>:<version> .` |
| 📦 Containers | List all containers | `docker ps -a` |
|  | List running containers | `docker ps` |
|  | Run container | `docker run <image_name>` |
|  | Run in background | `docker run -d <image_name>` |
|  | Custom container name | `docker run --name <name> <image>` |
|  | Port mapping | `docker run -p <host>:<container> <image>` |
|  | Set env vars | `docker run -e <var>=<value> <image>` |
|  | Start/Stop container | `docker start|stop <container>` |
|  | Remove container | `docker rm <container>` |
| 🧰 Troubleshoot | View logs | `docker logs <container>` |
|  | Shell inside container | `docker exec -it <container> /bin/bash` |
| ☁️ DockerHub | Pull image | `docker pull <image>` |
|  | Push image | `docker push <username>/<image>` |
|  | Login | `docker login -u <username>` |
|  | Search image | `docker search <image>` |
| 💾 Volumes | List volumes | `docker volume ls` |
|  | Create volume | `docker volume create <name>` |
|  | Delete volume | `docker volume rm <name>` |
|  | Mount named volume | `docker run --volume <vol>:<path> <image>` |
|  | Bind mount | `docker run --volume <host>:<container> <image>` |
| 🌐 Networks | List networks | `docker network ls` |
|  | Create network | `docker network create <name>` |
|  | Delete network | `docker network rm <name>` |
|  | Prune unused networks | `docker network prune` |

---

## 🧱 IMAGES

### 🔍 List All Local Images
```bash
docker images
