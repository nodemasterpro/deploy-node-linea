# Deploy Node Linea
This repository contains Ansible scripts for installing, updating, and removing a Linea node on Linux systems. The playbook simplifies the process of setting up a Linea node, managing its services, and ensuring that the node operations are streamlined.

## Prerequisites
- A Linux system (Ubuntu 22.04 LTS recommended) with root access.
- Git and Ansible 2.15 or newer installed on your machine.

## Getting Started
### Step 1: Installing Dependencies
Update your system's package list:

```
sudo apt update && sudo apt upgrade -y
```
Install Ansible and Git:
```
sudo apt install ansible git -y
```

### Step 2: Downloading the Project
Clone this repository to get the Ansible playbook and all necessary files:
```
git clone https://github.com/nodemasterpro/deploy-node-linea.git
cd deploy-node-linea
```

### Step 3: Executing the Playbook
Run the playbook using the following command. You will be prompted to specify the action (install or remove):
```
ansible-playbook linea_node.yml
```
Ensure you're running the playbook with root privileges or via a user with sudo access. The Linea node is started after installation.

### Step 4: Viewing Logs
To view the logs for the Linea node:
```
journalctl -u linea-node -f -o cat
```
### Additional Note
After installation, the Linea node's data directory is located at /root/linea_data. Ensure to check this location for your blockchain data.

Stopping Services
To stop the service:
```
sudo systemctl stop linea-node
```
Starting Services
To start the Linea node service:
```
sudo systemctl start linea-node
```
Remove Linea Node
To remove the Linea node, simply run the playbook again with the action set to remove:
```
ansible-playbook linea_node.yml -e node_action="remove"
```
Ensure to back up any important data before removing the Linea node, as this action may delete node data.





