# SecureCloud Baseline & CIS-Hardening Engine

> Automatisiertes, idempotentes Infrastructure-as-Code- und Configuration-Management-Framework zur Absicherung von Linux-Servern nach CIS-Benchmark Level 1 Standards (optimiert für Web-Agenturen und Cloud-Migrationen).

---

## 🚀 Über das Projekt
Dieses Projekt automatisiert die vollständige Sicherheits-Härtung und Basiskonfiguration von Ubuntu/Debian-Servern. Es schließt die Lücke zwischen schnellem Deployment (z.B. bei Cloud-Migrationen zu Hetzner) und strengen Compliance-Anforderungen, ohne den Betrieb von Web-Anwendungen (wie WordPress oder Node.js) zu gefährden.

## 🛡️ Abgedeckte CIS-Benchmark Sektionen & Rollen
Das Framework ist modular aufgebaut und in eigenständige Ansible-Rollen unterteilt:

* **`access_control`**: SSH-Hardening (Root-Login aus, Pubkey-only, Timeouts, sichere Auth-Tries).
* **`user_management`**: Password-Policies (Max/Min Days) und automatische Sperrung inaktiver Accounts.
* **`kernel_hardening`**: Sysctl-Optimierungen gegen IP-Spoofing, SYN-Floods und Kernel-Log-Schutz.
* **`firewall`**: UFW-Grundabsicherung (Default Deny In, Allow Out) mit definierten Standard-Ports.
* **`intrusion_prevention`**: Fail2ban-Integration zum automatischen Blockieren von Brute-Force-Angriffen.
* **`auditd`**: Erweitertes System-Auditing für sicherheitsrelevante Systemaufrufe.
* **`file_integrity`**: AIDE-Integration zur Überwachung der Dateisystem-Integrität.
* **`patch_management`**: Vollautomatisierte, sichere Sicherheits-Updates (Unattended Upgrades).
* **`services_cleanup`**: Attack Surface Reduction (Deinstallation veralteter Protokolle wie Telnet, TFTP, NIS).

---

## 🛠️ Tech Stack
* **Provisioning**: Terraform & Vagrant (für lokale Test-VMs)
* **Configuration Management**: Ansible (idempotent & modular)
* **CI/CD**: GitHub Actions (`ansible-lint` & Syntax-Checks)
* **Ziel-OS**: Ubuntu / Debian

---

## ⚙️ Quick Start (Lokales Testen)

1. **Repository klonen:**
   ```bash
   git clone [https://github.com/lschwe04/server-hardening.git](https://github.com/lschwe04/server-hardening.git)
   cd server-hardening