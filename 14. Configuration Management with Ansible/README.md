# Day 14 - Configuration Management with Ansible

## System Admin Responsibilities

- Installing, configuring, and updating server operating systems and applications
- Applying security patches and updates to the server
- Managing software licenses and ensuring compliance with vendor agreements
- and many more

## Why Configuration Management ?

- System Admin Responsiblities are simple to maintain for a few servers, but as the number of servers increase, the complexity of the management increases
- Due to the rise in cloud technology and microservices, number of servers have been tremendously increased
- This need of having automation of the server management lead to the concept of Configuration Management

## What is Configuration Management ?

- Configuration Management is the process of maintaining multiple servers in a desired, consistent state
- Some popular Configuration Management tools are
	- Puppet
	- Chef
	- Salt
	- Ansible

## Puppet vs Ansible

| Puppet | Ansible |
| -- | -- | 
| Pull Mechanism Model | Push Mechanism Model |
| Master Slave Model | Agentless Model |
| Tricky to manage Windows | Supports Windows and Linux |
| Complex to use| Simple to Use |

## Ansible Disadvantages

- Some Problems with Windows OS
- Debugging is not very easy
- Performance can be improved