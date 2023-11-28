# Day 23 - Introduction to Containers

## Why Containers ?

- Efficient usage of available resources can be achieved using Virtualization
- But this is not always the case, a 10 GB RAM virtual machine using 7GB RAM at most times is still not completely efficient
- This efficiency can be further increased by the use of containers

## What are Containers ?

- Containers are a bundle of Application, Application Libraries and System Dependencies, that run on a containerization platform
- They are light weight because they utilize the resources of Base Operating System, instead of having a seperate and complete Operating System
- Note that though the containers are more efficient, these are not as secure as an Virtual Machine, due to complete isolation and seperate OS of Virtual Machines

## Models of Containers

- Model 1
	- Containerization Platform is installed on top of a Physical Machine
- Model 2
	- Containerization Platform is installed on top of a Virtual Machine
	- This is more efficient in case of using Cloud Service Providers, because the maintainance of VMs is done by the Cloud

## Docker

- Docker is a containerization platform for creating and managing containers
- Instructions are written in Dockerfile and given to Docker Engine, which creates an Image
- This image when executed creates a container
- Disadvantages of Docker
	- Docker Engine becomes the single point of failure
	- A lot of layers are created along containers, which take up a lot of space