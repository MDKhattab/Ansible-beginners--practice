Here’s a clear and professional README.md draft for your conditional Ansible playbook:

# Ansible Playbook: Conditional Package Installation

This repository contains an Ansible playbook that demonstrates how to use **conditional logic** to install or remove packages depending on the operating system distribution. It’s a practical example of how Ansible can adapt tasks dynamically across heterogeneous environments.

## 📌 Features
- Detects the target host’s operating system using `ansible_facts`.
- Installs or removes `nginx` based on whether the host is running **CentOS** or **Ubuntu**.
- Ensures idempotency: tasks only run when conditions are met.

## 🛠️ Playbook Details
File: `install_nginx_withcondition.yml`

```yaml
---
- name: Install OS with condition
  hosts: web
  become: true
  tasks:
    - name: Install nginx on CentOS
      ansible.builtin.yum:
        name: nginx
        state: absent
      when: ansible_facts['distribution'] == "CentOS"

    - name: Install nginx on Ubuntu
      ansible.builtin.apt:
        name: nginx
        state: absent
      when: ansible_facts['distribution'] == "Ubuntu"

```

▶️ Execution
Run the playbook with:
ansible-playbook install_nginx_withcondition.yml


Expected Output:
![Expected Output](Captures%20-%20File%20Explorer%2009_03_2026%2012_25_33%20AM.png)

🚀 Use Cases
- Managing different Linux distributions in the same environment.
- Automating package installation/removal with OS-specific logic.
- Teaching conditional execution in Ansible for DevOps learners.
