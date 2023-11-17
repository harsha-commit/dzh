# Day 3 - Virtual Machines

## An Analogy for Virtual Machines

- Consider you have bought 2 acres of land and built a house on it
- You realized that your house and all other resources combined, takes up only 1 acre
- So, you built a house in the remaining 1 acre and rent it to a family
- This is an example of efficient usage of available resources, which is the core concept of **Virtualization**

### Note

- Server is just a computer that hosts an application, so that the clients can access it through the internet

## Before Virtualization

- Consider your team of developers created an application
- An application requires isolated environment and you need to serve multiple customers
- So, you deploy the copies of the application into 10 servers and each server has 50 GB RAM
- Later you realized that the application needs only 4 GB RAM, and the resources of the server are being under-utilized

## Virtualization

- Virtualization is the process of creating virtual machines from a physical machine
- Virtual machine is actually a software based computer, that utilizes a logical partition of the resources from a physical machine
- Note that each Virtual Machine has it's own Operating System
- The logical partitioning, isolation of the environments, configuration of OS, etc is managed by a software called as **Hypervisor**

## After Virtualization

- Now instead of using multiple servers that results mostly in under utilization, we can use Virtualization to use lesser number of servers and use available resources efficiently
- This concept of Virtualization eventually lead to Cloud Computing, which is one of the game changer in the Software Industry

## Virtualization in Cloud

- The Cloud Service Providers buy a large set of powerful computers across the globe 
- By virtualization, they provision the Virtual Machines with desired configuration in desired location, over the cloud
- This service is called Elastic Cloud Compute in AWS, Google Compute Engine in GCP Cloud
