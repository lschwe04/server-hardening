# Linux Server Hardening mit Ansible

Ein modulares und automatisiertes Ansible-Playbook zur Absicherung von Linux-Servern (getestet auf Ubuntu/Debian). Das Projekt folgt Best Practices für Security-Hardening, um die Angriffsfläche eines Servers signifikant zu verringern.

---

## 🛠️ Enthaltene Rollen & Features

Das Projekt ist in folgende logische Sicherheitsmodule (`roles`) unterteilt:

1. **`access_control`**: Härtung des SSH-Zugriffs (Deaktivierung von Root-Login und Passwörtern, Erzwingen von SSH-Keys, Limits für Login-Versuche) und Anpassung von `/etc/login.defs`.
2. **`firewall`**: Konfiguration von UFW (Uncomplicated Firewall) mit strikten Standard-Policies (eingehend `deny`, ausgehend `allow`) und Freigabe essenzieller Ports.
3. **`intrusion_prevention`**: Installation und Konfiguration von Fail2ban zum Schutz vor Brute-Force-Angriffen auf den SSH-Dienst.
4. **`kernel_hardening`**: Absicherung des Linux-Kernels über `sysctl`-Parametrisierung (Schutz vor IP-Spoofing, SYN-Floods, ICMP-Redirects und Einschränkung von Kernel-Logs).
5. **`patch_management`**: Automatisierte Sicherheitsupdates über `unattended-upgrades` inklusive optionalem, zeitgesteuertem Neustart bei Kernel-Updates.
6. **`services_cleanup`**: Bereinigung unnötiger und unsicherer Altlasten-Pakete (wie Telnet, rsh, tftp) sowie Absicherung kritischer Datei-Berechtigungen (`/etc/shadow`, `/etc/passwd`, etc.).

---

## 📂 Projektstruktur

```text
.
├── inventory/
│   └── hosts.ini          # Inventar-Datei (Ziele und Gruppen)
├── roles/
│   ├── access_control/
│   ├── firewall/
│   ├── intrusion_prevention/
│   ├── kernel_hardening/
│   ├── patch_management/
│   └── services_cleanup/
├── site.yml               # Zentrales Playbook
└── README.md