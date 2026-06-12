Here’s a cleaned-up, GitHub-ready version with clearer wording, consistent formatting, and a bit more precision.

***

# Docker Commands Cheat Sheet

## Basic Image Commands

**Pull the latest image**

```bash
docker pull <image-name>
```

Pulls the latest version of an image from Docker Hub (or another registry). If the image already exists locally, it will update it to the newest version.

**Pull a specific image version**

```bash
docker pull <image-name>:<tag>
```

Pulls a specific tagged version of an image (for example, `nginx:1.27`).

**List local images**

```bash
docker images
```

Shows all images that are stored locally on your Docker host.

***

## Container Lifecycle Commands

**Run an image (create + start a container)**

```bash
docker run <image-name>
```

Creates a new container from the image and runs it in the foreground. When the main process exits, the container stops.

**Run a container in interactive mode**

```bash
docker run -it <image-name>
```

Creates a container and attaches your terminal to it interactively (stdin/stdout). Useful for debugging or exploring the container.

**List containers**

```bash
docker ps
```

Shows all *running* containers.

```bash
docker ps -a
```

Shows all containers, including stopped ones.

**Stop a running container**

```bash
docker stop <container-id>   # or <container-name>
```

Gracefully stops a running container.

**Start a stopped container**

```bash
docker start <container-id>  # or <container-name>
```

Starts an existing (stopped) container.

**Remove a container**

```bash
docker rm <container-id>     # or <container-name>
```

Deletes a container. The container must be stopped first.

**Remove an image**

```bash
docker rmi <image-name>      # or <image-id>
```

Deletes an image from your local system. No containers may be using it.

***

## Running Containers: Useful Flags

**Run in detached (background) mode**

```bash
docker run -d <image-name>
```

Runs the container in the background (detached). Your terminal is not attached to its output.

**Run in detached mode with a custom container name**

```bash
docker run -d --name <container-name> <image-name>
```

Runs the container in the background and assigns it a human-readable name.

**Map host port to container port**

```bash
docker run -p <host-port>:<container-port> <image-name>
```

Binds a port on your host machine to a port inside the container (for example, `-p 8080:80`).

***

## Logs and Shell Access

**View container logs**

```bash
docker logs <container-id>   # or <container-name>
```

Shows the logs produced by the container’s main process. Very useful for troubleshooting.

You can also follow logs in real time with:

```bash
docker logs -f <container-id>
```

**Get a shell inside a running container**

```bash
docker exec -it <container-id> /bin/bash
# or
docker exec -it <container-id> /bin/sh
```

Starts an interactive shell inside an already running container. Exiting the shell does *not* stop the container.

***

## Docker Network Commands

**List networks**

```bash
docker network ls
```

Shows all Docker networks available on the host.

**Create a network**

```bash
docker network create <network-name>
```

Creates a new user-defined network.

**Remove a network**

```bash
docker network rm <network-name>
```

Deletes a network. It must not be in use by any containers.

***

## Docker Compose Commands

**Start services from a Compose file**

```bash
docker compose -f <compose-file> up -d
```

Creates and starts all services defined in the given Compose file (`docker-compose.yml` / `compose.yaml`) in detached mode.

**Stop and remove services**

```bash
docker compose -f <compose-file> down
```

Stops containers and removes containers, networks, and default volumes created by `up`.

***

## Building and Pushing Images

**Build an image from a Dockerfile**

```bash
docker build -t <image-name>:<tag> .
```

Builds an image using the Dockerfile in the current directory and tags it (for example, `my-app:1.0`).

**Log in to a Docker registry**

```bash
docker login
```

Authenticates your Docker client with Docker Hub or another registry.

**Push an image to a registry**

```bash
docker push <username>/<image-name>:<tag>
```

Pushes your image to Docker Hub (or another registry), making it available to pull on other machines.

***

## Docker Volumes (Persistent Data)

**Run a container with a bind mount**

```bash
docker run -it -v <host-path>:<container-path> <image-name>
```

Mounts a host directory into the container. Changes in the container path are reflected on the host, and vice versa.

**List volumes**

```bash
docker volume ls
```

Shows all named Docker volumes.

**Create a named volume**

```bash
docker volume create <volume-name>
```

Creates a managed Docker volume (stored under `/var/lib/docker/volumes` by default).

**Remove a named volume**

```bash
docker volume rm <volume-name>
```

Deletes a volume that is not currently in use by any container.

**Run a container with a named volume**

```bash
docker run -v <volume-name>:<container-path> <image-name>
```

Attaches an existing named volume (or creates it if it doesn’t exist) to the container path.

**Run a container with an anonymous volume**

```bash
docker run -v <container-path> <image-name>
```

Creates an anonymous (unnamed) volume managed by Docker and mounts it at the given path inside the container.

**Remove unused volumes**

```bash
docker volume prune
```

Removes all unused (dangling) volumes to free space.

***

If you want, I can wrap this into a markdown file structure like:

- `README.md` with a short intro  
- `docker-commands.md` for this cheat sheet  

so you can drop it straight into a GitHub repo.
