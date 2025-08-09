# ansible-nginx-deployment

Automated Nginx Deployment with Ansible
This project demonstrates how to use Ansible to automatically install and start Nginx on a remote server (AWS EC2 in this case).
📌 Project Overview
* The goal is to automate the process of installing and configuring Nginx without manually logging into the server.
* Using Ansible, we define the tasks in a YAML playbook and run them on the target server through SSH.

🛠 Tools & Technologies
* Ansible (Configuration Management)
* AWS EC2 (Ubuntu 20.04)
* Nginx (Web Server)
* SSH for remote connection

📂 Project Structure
```bash

├── install_nginx.yml   # Ansible playbook to install & start Nginx
├── inventory           # Inventory file with target server details
```
🚀 How to Run
1. Clone this repository

```bash
git clone https://github.com/yourusername/ansible-nginx-deployment.git
cd ansible-nginx-deployment
```
2. Update the inventory file
Replace with your server’s IP address and SSH username:

```bash
[web]
your-server-ip ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem
```
3. Run the playbook
```bash
ansible-playbook -i inventory install_nginx.yml
```
4. Verify Installation
SSH into your server and check:

```bash
nginx -v
```
📷 Sample Output
markdown
```
PLAY [Install and start nginx] *************************************************

TASK [Gathering Facts] *********************************************************
ok: [your-server-ip]

TASK [Install Nginx] ***********************************************************
changed: [your-server-ip]

TASK [Start Nginx] *************************************************************
changed: [your-server-ip]

PLAY RECAP *********************************************************************
your-server-ip              : ok=3   changed=2   unreachable=0   failed=0

```
📚 Learnings
* Automating web server setup with Ansible saves time and reduces errors.
* Infrastructure as Code (IaC) principles help maintain consistent environments.
