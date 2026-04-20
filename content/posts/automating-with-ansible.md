---
title: "Automating Infrastructure with Ansible"
date: 2026-04-15T12:00:00Z
draft: false
tags: ["Ansible", "DevOps"]
---

Ansible is an open-source automation tool that simplifies configuration management, application deployment, and task automation.

## Why Ansible?

Ansible uses a simple syntax written in YAML called playbooks. It's agentless, meaning you don't need to install any software on the target nodes.

## A Simple Playbook

Here is an example playbook that updates apt cache and installs `nginx`:

```yaml
---
- name: Setup Web Server
  hosts: webservers
  become: yes
  
  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes
        
    - name: Install Nginx
      apt:
        name: nginx
        state: present
        
    - name: Ensure Nginx is running
      service:
        name: nginx
        state: started
        enabled: yes
```

To run this playbook, you'd use the `ansible-playbook` command:

```bash
ansible-playbook -i inventory.ini setup-web.yaml
```

Ansible makes it incredibly easy to manage complex deployments at scale.
