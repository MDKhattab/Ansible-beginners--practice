# Ansible Playbook: Install and Verify Packages

This repository demonstrates an Ansible playbook that installs, verifies, and reports on essential packages across multiple web servers. It highlights how automation ensures consistency and reliability in infrastructure management.

## 📌 Features
- Installs multiple packages (`nginx`, `httpd`, `git`) on target hosts.
- Uses conditional logic to install only required packages.
- Verifies installation using `rpm -q`.
- Prints a clear result message for transparency.

## 🛠️ Playbook Details
File: `install_packages.yml`

```yaml
---
- name: Install Packages
  hosts: web
  become: true
  vars:
    packages:
      - name: nginx
        required: true
      - name: httpd
        required: true
      - name: git
        required: true

  tasks:
    - name: install packages
      ansible.builtin.yum:
        name: "{{item.name}}"
        state: present
      when: item.required == true
      loop: "{{ packages }}"

    - name: verify installation
      ansible.builtin.shell: "rpm -q {{item.name}}"
      register: result
      loop: "{{ packages }}"

    - name: print result
      ansible.builtin.debug:
        var: result.msg
```


the expected result 
![ the output ](install_packages.yml%20-%20Day%202%20-%20Visual%20Studio%20Code%2008_03_2026%2011_22_50%20PM.png)