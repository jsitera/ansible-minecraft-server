# ansible-minecraft-server
Automated setup of Minecraft server in the cloud VM using Docker and Ansible.
Using https://github.com/itzg/docker-minecraft-server
Support for not-so-automated management via docker-compose.
Support for specific rules of virtualization provided by University of West Bohemia (https://support.zcu.cz/index.php/Cloudov%C3%A9_slu%C5%BEby).

# Usage
Create a VM in cloud with at least 4GB RAM, setup root access via SSH.

Clone the repository, add hosts file with your VM address and run the ansible script.

Hosts file example
```
[all]

[all:vars]
ansible_ssh_common_args='-o StrictHostKeyChecking=no'
ansible_user=root

[main]
VM1 ansible_host=xx.xx.xx.xx
```
Ansible command 
```
ansible-playbook stack.yml -l VM1
```

# roles
* basics - basic setup of VM
* minecraft-user - create user minecraft where all all services are running
* remote-access - setup remote access to the VM (via SSH with keys)
* docker - install docker - deprecated - i'm using geerlingguy.docker
* minecraft-docker - configure minecraft docker container, alternatively use docker-compose.yml

# TODO/Limitations
* Better handling of options, for now please edit the appropriate main.yml files.
