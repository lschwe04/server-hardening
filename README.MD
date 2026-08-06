Server Hardening
Automated Linux server hardening using Ansible.

Overview
This repository contains Ansible roles and playbooks to secure and harden Linux systems. It includes automated linting via GitHub Actions to ensure code quality and compliance.

Project Structure

├── .github/workflows/    # CI/CD pipelines (Ansible Lint)
├── roles/
│   ├── access_control/   # User access, password policies, and security limits
│   └── auditd/           # Audit daemon configuration and system event auditing
└── README.md

Requirements
Ansible >= 2.10

Ansible-Lint (for local development and testing)

Quick Start
1. Clone the repository: git clone https://github.com/lschwe04/server-hardening.git
cd server-hardening

2. Run ansible-lint locally to check for syntax and style compliance: ansible-lint

3. Execute the playbook: ansible-playbook -i inventory.ini playbook.yml

CI/CD Pipeline
The GitHub Actions workflow automatically runs ansible-lint on every push to the main branch to enforce FQCN usage, variable naming conventions, and proper YAML formatting.