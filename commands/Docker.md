# Docker Commands Reference

This document contains commonly used Docker commands for managing containers, images, volumes, and Docker Compose.

---

## 🐳 Docker Basic Container Commands

```bash
docker start <container-name>
docker stop <container-name>
docker restart <container-name>
docker status <container-name>
docker rm <container-name>
```

* Start / stop / restart containers
* Remove stopped containers

---

## 📦 Docker Container Management

```bash
docker ps
docker ps -a
docker logs <container-name>
docker logs -f <container-name>
docker exec -it <container-name> bash
docker inspect <container-name>
```

* List running / all containers
* View container logs
* Access container shell
* Inspect container details

---

## 🧱 Docker Image Commands

```bash
docker images
docker pull <image-name>
docker rmi <image-id>
docker rmi -f <image-id>
docker image prune -f
docker system prune -a
```

* List images
* Pull images from Docker Hub
* Remove unused or dangling images

---

## 📁 Docker Volume Commands

```bash
docker volume ls
docker volume inspect <volume-name>
docker volume rm <volume-name>
docker volume prune -f
```

* Manage persistent data storage

---

## 🌐 Docker Network Commands

```bash
docker network ls
docker network inspect <network-name>
docker network rm <network-name>
```

* Manage Docker networks

---

## 🧩 Docker Compose Commands

```bash
docker compose up
docker compose up -d
docker compose down
docker compose build
docker compose ps
docker compose logs
```

* Start and stop multi-container applications
* Run containers in detached mode

---

## 🛠️ Docker Cleanup Commands

```bash
docker container prune
docker container prune -f
docker image prune -f
docker volume prune -f
docker system prune -a
```

* Clean unused containers, images, volumes, and networks

---

## 📌 Helpful Tips

* Use `-f` carefully; it force removes resources
* Always check running containers before pruning
* Prefer `docker compose down` instead of manual cleanup

---

## ✅ Recommended Usage Flow

1. Build or pull image
2. Start containers using Docker Compose
3. Monitor logs
4. Stop and clean unused resources periodically
