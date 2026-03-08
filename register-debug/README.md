Here’s a professional README.md draft for your Ansible playbook that uses register and debug to capture and display command output:

# Ansible Playbook: Register & Debug Example

This repository contains an Ansible playbook that demonstrates how to use the **`register`** and **`debug`** modules to capture command output and display it during playbook execution. This is a common technique for troubleshooting and validating automation workflows.

## 📌 Features
- Executes a shell command on remote hosts.
- Registers the output for later use.
- Prints the results using the `debug` module.
- Demonstrates filtering `/etc/passwd` for entries containing `root`.

## 🛠️ Playbook Details
File: `register-debug.yml`

```yaml
---
- name: check /etc/passwd file
  hosts: web
  become: true
  tasks:
    - name: check /etc/passwd file
      ansible.builtin.shell: cat /etc/passwd | grep root
      register: passwd_file

    - name: debug /etc/passwd file
      ansible.builtin.debug:
        var: passwd_file.stdout_lines
```

▶️ Execution
Run the playbook with:
ansible-playbook register-debug.yml


Expected Output:
![Expected Output](install_nginx_withcondition.yml%20-%20Day%202%20-%20Visual%20Studio%20Code%2009_03_2026%2012_32_14%20AM.png)

🚀 Use Cases
- Debugging and validating command outputs during automation.
- Capturing system information for reporting or conditional logic.
- Teaching Ansible fundamentals for DevOps learners.
