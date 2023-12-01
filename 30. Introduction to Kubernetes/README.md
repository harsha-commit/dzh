# Day 30 - Introduction to Kubernetes

## Problems with Docker

- Single Host
	- Consider there are 99 containers that are using the maximum resources from the host
	- Now when a new container is created, due to lack of resources it is destroyed
	- Though this container is independent of all other containers, it is getting affected
	- This problem arises due to lack of resources, which inturn points out to using only single host for the service
- Manual healing
	- If a container goes down, it directly affects the application that was running
	- To avoid this one has to monitor continuously and restart containers on time
	- This manual effort is very difficult and not optimal
- Manual Scaling and No Load balancing
	- The containers must scale up or down, based on the workload
	- To implement scaling, corresponding load balancing becomes a requirement
	- There is only manual scaling and no load balancing with respect to Docker
- Docker doesn't provide any enterprise level support which includes
	- Firewall
	- Load Balancer
	- Auto Scaling
	- Auto Healing
	- API Gateways, etc

## Kubernetes

- Docker is a container platform, Kubernetes is a container orchestration platform
- The problems mentioned of the Docker are solved by Kubernetes
- Kubernetes is a cluster based, master slave architecture platform
- It has multiple master nodes and multiple worker nodes

## Advantages of Kubernetes

- Because of multiple worker nodes, if a container fails in a node, it is assigned to another node
- Scaling of containers is done by 
	- Replica Set
		- The no. of replicas (mentioned in replica set) of a container are maintained
	- Horizontal Pod AutoScaler
		- The scaling of containers is done based on the specified parameters
- Healing
	- Using API Server, if a container goes down, a new container is rolled out automatically
- Kubernetes, backed up by CNCF,  is originated from a Google product called Borg
	- It was made as an Enterprise Level Container Orchestration Platform
- Flexible
	- It provides concepts like Custom Resource, Custom Resource Definitions which makes Kubernetes very extensible
	- Advanced Load Balancing was achieved using Ingress Controllers, which is actually an extension of Kubernetes