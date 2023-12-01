# Day 33 - Kubernetes Pods

## Pods

- Smallest unit of Kubernetes, wraps a container
- Definition of how to run a container
- Instead of commands instructions are written in a YAML file, which makes it easy to read
- For Enterprise Level, it brings out standardization and declarative capabilities
- For a multi-container pods, Kubernetes will allow
	- Shared Networking
	- Shared Storage
- Kube-proxy allocates Cluster IP Addresses for Pods, we access containers using this address

## Kubectl

- command line for Kubernetes for interacting with kube-apiserver

## Deploy a Pod in Minikube

- Install Kubectl
- Install Minikube
- Create `pod.yaml` file and write the below code
- To create the pod, `kubectl create -f pod.yaml`
- To verify, `kubectl get pods`
- Refer kubectl cheatsheet

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```