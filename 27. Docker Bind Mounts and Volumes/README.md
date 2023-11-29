# Day 27 - Docker Bind Mounts and Volumes

## Problems with Containers

- Containers are ephemeral (short lived)
- If a container is down, all the data inside the container is lost
- Any dependencies of a container will be effected if the data is not persistent
- If a container wants to read data from host machine, there is no direct way

## Bind Mounts

- Bind mounts binds a directory of host machine to a directory of the container
- So even if the container is down, the data persists at host machine

## Volumes

- Volumes are logical partitions of memory on the host machine
- Volumes can be created, destroyed, shared among containers, removed and attached to other containers
- In this, the directory of the host machine where the data is stored is not mentioned
- Volumes lifecycle can be managed through CLI itself, independent of containers
- Volumes can be created on Host Machine, EC2 Instance, S3 Buckets, NFS, etc
- External storages can provide more space and performance

## Hands on

```sh
# List all volumes
docker volume ls

# Delete a volume
docker volume rm <VOLUME_NAME>

# Create a volume
docker volume create my-volume

# Show details of a volume (Created At, Mount Point, etc)
docker volume inspect my-volume

# Mount the volume to the container
docker run -d --mount source=my-volume,target=/app nginx:latest

# Show details of a container
docker inspect <CONTAINER_ID>
```