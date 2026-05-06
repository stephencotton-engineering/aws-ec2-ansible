# AWS EC2 Automation — Ansible

Automated EC2 instance configuration and application deployment using Ansible. Eliminates manual server setup by defining infrastructure configuration as repeatable, version-controlled playbooks.

---

## What This Builds

- Ansible inventory defining target EC2 instances
- Playbooks that automate server configuration end to end
- Roles for organized, reusable automation tasks
- Automated installation and configuration of a web server
- System hardening tasks including user management and SSH configuration
- Idempotent playbooks that can be run multiple times safely

---

## Project Structure

```
aws-ec2-ansible/
├── inventory/
│   └── hosts.ini             # Defines target EC2 instances
├── playbooks/
│   ├── site.yml              # Master playbook — runs everything
│   ├── webserver.yml         # Web server installation and config
│   └── hardening.yml         # Basic system hardening
├── roles/
│   └── webserver/
│       ├── tasks/
│       │   └── main.yml      # Tasks to install and configure web server
│       ├── handlers/
│       │   └── main.yml      # Handlers triggered by task changes
│       └── templates/
│           └── index.html.j2 # Jinja2 template for web page
├── ansible.cfg               # Ansible configuration file
└── README.md
```

---

## Prerequisites

- Ansible installed on your local machine
- AWS EC2 instances running Amazon Linux 2
- SSH key pair configured for EC2 access
- Target instance IPs added to inventory/hosts.ini

---

## Usage

```bash
# Test connectivity to all hosts
ansible all -m ping -i inventory/hosts.ini

# Run the full site playbook
ansible-playbook playbooks/site.yml -i inventory/hosts.ini

# Run only the web server playbook
ansible-playbook playbooks/webserver.yml -i inventory/hosts.ini

# Run with verbose output for debugging
ansible-playbook playbooks/site.yml -i inventory/hosts.ini -v
```

---

## Key Concepts Demonstrated

- Ansible inventory and host grouping
- Playbooks and task organization
- Ansible roles for reusable automation
- Jinja2 templates for dynamic configuration
- Handlers for service management
- Idempotent configuration management

---

## Stack

![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
