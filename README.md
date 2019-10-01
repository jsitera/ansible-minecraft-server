# ansible-minecraft-server
Automated setup of Minecraft server in the cloud VM using Docker and Ansible.

# Usage

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
