# Ansible-Playbook: Monit

Sample usage:

```
# Install Monit on all hosts
---
- hosts: all
  roles:
    # Install monit
    - { role: monit }
  tasks:
    - user: name=pgolm groups='monit'

# Define Monitors on some nodes
- hosts: ssh-hosts
  vars:
    monit_services:
      - sshd
  roles:
    - { role: monit, services: monit_services }
```