### Chapter 1: Creating and Running Containers

#### Key Points

**Docker Fundamentals**
- Images: Read-only templates used to create containers. They contain the application code, libraries and configurations.
- Containers: Running instances of an image. They are isolated from each other and the host system.
- Dockerfile: A text file with instructions for building a Docker image. It defines the base image, dependencies and commands to run.
- Docker CLI: A command-line tool for interacting with Docker, used to build, run and manage containers and images.

**Building Effective Images**
- Choosing the right base image: Start with a minimal base image to reduce size and improve security (you're avoiding unnecesary packages).
- Minimizing Layers: Each instruction in a Dockerfile creates a new layer, so keep them conciese to reduce image size.
- Caching: Docker caches layers to speed up builds, so order instructions from least to most frequently changed.
- Multi-Stage Builds: Use multiple stages to separate build-time dependencies from runtime dependencies, resulting in smaller images.

**Running Containers**
- ``docker run -d --name <container_name> <image_name>`` command: Used to start a container from an image.
- Port Mapping: Expose container ports to the host machine to make the application accessible. You can do it adding ``docker run ... --publish <host_port>:<container_port> ...``.
- Volume Mounting: Mount host directories into the container to persist data and share files.
- Limiting Resources: Take control of the container resources. It allow you to control essential resources as CPU, memory and memory swap.

**Cleanup**
- Removing images: An image can be removed using ``docker rmi <tag_name>`` or ``docker rmi <image_id>``.
- General cleanup: Use ``docker system prune`` to remove all stopped containers, all untagged images and all unused image layers cached.

