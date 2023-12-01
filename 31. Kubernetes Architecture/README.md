# Day 31 - Kubernetes Architecture

## Architecture Diagram

![](https://devopscube.com/wp-content/uploads/2022/12/k8s-architecture.drawio-1.png)

## Worker Node / Data Plane

### Pod

- smallest unit of Kubernetes
- essentially a wrapper for containers when deploying them in Kubernetes

### Container Runtime

- Every container requires a Container Runtime to run
- Docker uses Docker-shim as its Container Runtime
- Kubernetes supports Dockershim, CRI-O, containerd, etc container runtimes that implement Kubernetes Container Runtime Interface

### Kubelet

- Responsible for creating and maintaining pods
- Monitors the pods, signals the master in case of pod failure

### Kube-proxy

- Responsible for pod networking, uses IP tables internally
- Also provides load balancing capability

## Master Node / Control Plane

### API Server

- exposes Kubernetes to external world
- core component, takes up all the requests

### Kube Scheduler

- schedules pods on nodes

### etcd

- key value store, acts as backing store
- stores all cluster data

### Controller Manager

- Manages Replica Set Controller
- Ensures that a controller is always running

### Cloud Controller Manager

- The request from cloud service provider is translated to Kubernetes request by CCM