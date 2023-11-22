# Day 15 - Ansible Zero to Hero

## Prerequisites

- Create an Ubuntu EC2 Instance and name it Ansible Server
- Create another Ubuntu EC2 Instance and name it Target Server

## Installing Ansible on Ansible Server

- Install updates 
	- `sudo apt update`
- Install ansible 
	- `sudo apt install ansible`
- Verify by
	- `ansible --version`

## Setting up Password-less Authentication

- Generate SSH Keys in both servers
	- `ssh-keygen`, press Enter for all prompts
- Copy public key from Ansible server
	- `cat .ssh/id_rsa.pub`
- Append this public key into authorized key file of Target server
	- `vi .ssh/authorized_keys`
- Verify the connection in Ansible Server by
	- `ssh <PRIVATE_IP_ADDRESS_OF_TARGET_SERVER>`

## Configuring the Inventory file

- Write the IP Addresses of the managed servers in the file
- We can group a set of IP Address and name them using section headers

```text
[dbservers]
172.31.45.114

[webservers]
172.31.45.200
```

## Ansible Playbooks

- Two ways of executing Ansible tasks
	- Adhoc commands - for simpler tasks
	- Playbooks - for verbose/ complex tasks

### Example Commands

```sh
# Creates a file in Target server for all servers in inventory file
ansible all -i /home/ubuntu/inventory -m "shell" -a "touch test"

# Creates a file in Target server for the specified group in inventory file
ansible webservers -i /home/ubuntu/inventory -m "shell" -a "touch test"
```

### Example Playbooks

```yaml
# vi first_playbook.yml
# ansible-playbook -i /home/ubuntu/inventory first_playbook.yml
# ansible-playbook -v -i /home/ubuntu/inventory first_playbook.yml (Verbose)
# Refer documentation for desired modules

---
- name: Install and Start nginx
  hosts: all
  become: true

  tasks:
  - name: Install nginx
    apt:
      name: nginx
      state: present
      update_cache: true
  - name: Start nginx
	service:
	  name: nginx
	  state: started
```

## Ansible Roles

- Ansible roles are used to write structured and efficient playbooks
- Examples at https://github.com/ansible/ansible-examples

### Ansible Roles File Structure

- **defaults:** Contains default values for variables used within the role 
- **files:** Holds static and dynamically generated files that the role deploys or manipulates
- **handlers:** Defines handlers, which are tasks that are triggered by events or notifications from other parts of the playbooks or roles
- **meta:** Stores metadata about the role, such as its name, description, author, license, dependencies, and supported platform information
- **tasks:** Contains the main list of tasks to be executed by the role. These tasks define the actions that the role performs on the target hosts
- **templates:** Houses Jinja2 template files that the role utilizes to render configuration files or other content
- **tests:** Includes unit tests and integration tests for the role's functionality
- **vars:** Contains additional variables specific to the role. These variables can be overridden in the playbooks that use the role