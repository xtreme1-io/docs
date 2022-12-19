---
sidebar_position: 3
---

# Install from Source

If you want to build or extend the functionality, consider downloading the source code using Git and running Xtreme1 locally:


## Enable Docker BuildKit

Use Docker BuildKit to accelerate the building speed, such as cache Maven and NPM packages between builds. 
By default, BuildKit is not enabled in Docker Desktop, you can enable it as following. 
For more details, you can check the official document [Build images with BuildKit](https://docs.docker.com/develop/develop-images/build_enhancements/).

```bash
# Set environment variable to enable BuildKit just for once.
DOCKER_BUILDKIT=1 docker build .
DOCKER_BUILDKIT=1 docker compose up

# Or edit Docker daemon.json to enable BuildKit by default, the content can be something like '{ "features": { "buildkit": true } }'.
vi /etc/docker/daemon.json

# You can clear builder cache if you encounter some package version related problem.
docker builder prune
 ```

### Clone repository

```bash
git clone https://github.com/basicai/xtreme1.git
cd xtreme1
```

### Build images and run services

The `docker-compose.yml` default will pull application images from Docker Hub, if you want to build images from source code, you can comment service's image line and uncomment build line.

```yaml
services:
  backend:
    # image: basicai/xtreme1-backend
    build: ./backend
  frontend:
    # image: basicai/xtreme1-frontend
    build: ./frontend
```

Then when you run `docker compose up`, it will first build `backend` and `frontend` image and start services. Be sure to run `docker compose build` when code changed, as up command will only build image when it not exist.

> You should not commit your change to `docker-compose.yml`, to avoid this, you can copy `docker-compose.yml` to a new file `docker-compose.develop.yml`, and modify this file as your development need, as this file is already added into `.gitignore`. And you need to specify this specific file when running Docker Compose command, such as `docker compose -f docker-compose.develop.yml build`.

If you face additional issues, [please let us know.](https://github.com/basicai/xtreme1/issues)