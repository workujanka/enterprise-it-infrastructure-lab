# enterprise-it-infrastructure-lab

A complete, end‑to‑end IT infrastructure lab designed to simulate real enterprise environments using VirtualBox, Windows Server, Linux servers, Active Directory, DNS, DHCP, Group Policy, and core system administration practices.  
This project serves as a learning environment, documentation reference, and professional portfolio showcase for modern system administration.

---

## 🌐 Project Overview

This lab replicates a hybrid Windows–Linux infrastructure commonly found in enterprise networks.  
It includes:

- Virtualization using VirtualBox  
- Windows Server domain controller  
- Windows client machines  
- Linux web and database servers  
- Enterprise networking (DNS, DHCP, routing)  
- Group Policy management  
- Server hardening and security  
- Automation scripts (PowerShell + Bash)  
- Troubleshooting guides  
- Future expansion for monitoring, backups, cloud, and more  

The goal is to build a realistic, fully documented IT environment that demonstrates practical system administration skills.

---

## 🏗️ Infrastructure Components

### **Windows Environment**
- **WIN-DC01** — Domain Controller (AD DS, DNS, DHCP)
- **WIN-CLIENT03** — Windows 10/11 domain‑joined workstation

**Future Windows servers:**
- File server  
- WSUS update server  
- Secondary domain controller  
- RADIUS/NPS authentication server  
- Windows Admin Center host  

---

### **Linux Environment**
- **LNX-WEB01** — Web server (Apache/Nginx)
- **LNX-DB01** — Database server (MySQL/PostgreSQL)

**Future Linux servers:**
- Monitoring server (Prometheus, Grafana, Zabbix)
- Reverse proxy (Nginx/HAProxy)
- Backup server
- Container host (Docker/Podman)
- Logging server (ELK/Graylog)

---

### **Networking**
- VirtualBox NAT + Internal Network  
- DNS (AD‑integrated)  
- DHCP with enterprise options  
- Routing and gateway configuration  

---

## 📁 Repository Structure

```
enterprise-it-infrastructure-lab/
│
├── README.md
│
├── docs/
│   ├── 01-virtualization/
│   ├── 02-windows-server-setup/
│   ├── 03-active-directory/
│   ├── 04-dns/
│   ├── 05-dhcp/
│   ├── 06-group-policy/
│   ├── 07-linux-servers/
│   ├── 08-linux-projects/
│   ├── 09-windows-projects/
│   └── 10-troubleshooting/
│
├── projects/
│
├── scripts/
│   ├── powershell/
│   └── bash/
│
└── tests/
```

Each folder contains structured, numbered documentation for easy navigation and long‑term reference.

---

## 🎯 Learning Objectives

This lab demonstrates practical skills in:

- Virtual machine deployment  
- Windows Server administration  
- Active Directory design  
- DNS and DHCP configuration  
- Group Policy management  
- Linux server administration  
- Web and database service deployment  
- Network troubleshooting  
- Automation with PowerShell and Bash  
- Documentation and version control  

---

## 📘 Documentation Style

All documentation follows a consistent format:

- Numbered sections  
- Step‑by‑step instructions  
- Screenshots (optional)  
- Commands and configuration examples  
- Troubleshooting notes  
- Best practices  

This ensures clarity for both beginners and experienced administrators.

---

## 🚀 Future Enhancements

Planned expansions include:

- Monitoring stack (Prometheus, Grafana, Zabbix)  
- Centralized logging (ELK/Graylog)  
- Backup and restore workflows  
- Security hardening guides  
- Cloud integration (Azure AD, hybrid join)  
- Containerization (Docker, Podman)  
- CI/CD for infrastructure scripts  

---

## 📄 License

This project is open for learning and personal development.  
Feel free to fork, modify, and build upon it.

---

## 🙌 Author

Created by **Worku**  
System Administration | Windows | Linux | Networking | Virtualization
