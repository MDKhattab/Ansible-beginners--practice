Here’s a comprehensive README.md that ties together all your Ansible practice projects into one well-organized portfolio:

# 🛠️ Ansible Practice Projects

This repository showcases a series of beginner-to-intermediate Ansible playbooks designed to automate common infrastructure tasks. Each playbook demonstrates a specific concept or feature of Ansible, helping build a strong foundation in configuration management and DevOps automation.

## 📁 Project Structure

| Folder | Description |
|--------|-------------|
| `install_packages-with-Ansible` | Installs packages (`nginx`, `httpd`, `git`) across multiple hosts using conditional logic. |
| `create_users` | Creates multiple user accounts using a loop and variable list. |
| `check-diff` | Demonstrates Ansible's `--check` and `--diff` modes for safe previewing and validation. |
| `install_nginx_withcondition` | Installs or removes `nginx` based on OS type (CentOS vs Ubuntu) using `ansible_facts`. |
| `register-debug` | Captures and prints command output using `register` and `debug` modules. |

---

## 📌 Key Concepts Covered

- ✅ Package installation with loops and conditions
- 👥 User creation automation
- 🔍 Check mode and diff mode for safe validation
- 🧠 Conditional execution based on OS
- 🖥️ Output registration and debugging

---

## ▶️ How to Run

Each playbook can be executed using:

```bash
ansible-playbook <playbook-name>.yml

For check/diff mode examples:
ansible-playbook check-diff/check-mode.yml --check
ansible-playbook check-diff/diff-mode.yml --check --diff

```

🚀 Learning Goals
- Build reproducible, scalable automation workflows
- Understand Ansible modules and task structure
- Practice safe deployment strategies
- Gain confidence in Infrastructure as Code

📷 Visual Summary
![Ansible Automation](Ansible%20automation%20w.png)


