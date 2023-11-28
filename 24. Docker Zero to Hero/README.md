# Day 24 - Docker Zero to Hero

## Files and Folders in containers base images

```text
/bin: contains binary executable files, such as the ls, cp, and ps commands.

/sbin: contains system binary executable files, such as the init and shutdown commands.

/etc: contains configuration files for various system services.

/lib: contains library files that are used by the binary executables.

/usr: contains user-related files and utilities, such as applications, libraries, and documentation.

/var: contains variable data, such as log files, spool files, and temporary files.

/root: is the home directory of the root user.
```

## Files and Folders that containers use from host operating system

```text
The host's file system: Docker containers can access the host file system using bind mounts, which allow the container to read and write files in the host file system.

Networking stack: The host's networking stack is used to provide network connectivity to the container. Docker containers can be connected to the host's network directly or through a virtual network.

System calls: The host's kernel handles system calls from the container, which is how the container accesses the host's resources, such as CPU, memory, and I/O.

Namespaces: Docker containers use Linux namespaces to create isolated environments for the container's processes. Namespaces provide isolation for resources such as the file system, process ID, and network.

Control groups (cgroups): Docker containers use cgroups to limit and control the amount of resources, such as CPU, memory, and I/O, that a container can access.
```

## What is Docker ?

- Docker is a tool that implements the concept of containerization
- It is a containerization platform that provides easy ways to
	- build container images
	- run the images to create containers
	- push containers to container registries and so on

## Docker Architecture

![](https://user-images.githubusercontent.com/43399466/217507877-212d3a60-143a-4a1d-ab79-4bb615cb4622.png)

## Docker Lifecycle

![](https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png)

## Docker Terminology

- Docker daemon: Manages Docker objects
- Docker client: Interacts with Docker daemon
- Docker Desktop: Easy-to-install application for building and sharing containerized applications
- Docker registries: Store and Share Docker images
- Docker objects: Images, containers, networks, volumes, plugins of Docker
- Dockerfile: File with steps to build a Docker image

---

## Docker in Action

- Create an Ubuntu EC2 Instance on AWS and run the below commands to install docker.

```sh
# Update the package manager
sudo apt update

# Install the Docker
sudo apt install docker.io -y

# Check if Docker Daemon is running
sudo systemctl status docker

# Start the Docker Daemon (If it is not running)
sudo systemctl start docker

# Add User to docker linux group
# Docker runs using root user
sudo usermod -aG docker ubuntu

# RESTART THE INSTANCE

# Verify by running
docker run hello-world

# Clone the repository and move to example folder
git clone https://github.com/iam-veeramalla/Docker-Zero-to-Hero
cd examples/first-docker-file

# Login to Docker (give credentials of your Docker Hub Account)
docker login

# Build the Image
docker build -t <YOUR_DOCKER_HUB_USER_NAME>/my-first-docker-image:latest .

# Verify if images is created
docker images

# Run your first docker container
docker run -it <YOUR_DOCKER_HUB_USER_NAME>/my-first-docker-image

# Push the image to DockerHub
docker push <YOUR_DOCKER_HUB_USER_NAME>/my-first-docker-image
```