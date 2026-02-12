# 04 — VirtualBox Networking Modes

This section explains the networking modes used in the enterprise IT infrastructure lab. Understanding these modes is important before configuring the internal network and connecting the Windows and Linux machines.

---

## 1. Overview of VirtualBox Networking

VirtualBox provides several networking modes. The lab uses only two of them:

- **NAT** — for internet access  
- **Internal Network** — for isolated communication between lab machines  

These two modes together create a realistic enterprise-style environment.

---

## 2. NAT Mode

NAT (Network Address Translation) allows a virtual machine to access the internet through the host system.

### Key points

- VM can reach the internet  
- VM cannot be reached from the internet  
- No configuration required  
- Useful for downloading updates and packages  

In this lab, **Adapter 1** on every VM uses **NAT**.

---

## 3. Internal Network Mode

Internal Network creates a private, isolated network that only VirtualBox VMs can access.

### Key points

- VMs can communicate with each other  
- VMs cannot reach the host  
- VMs cannot reach the internet  
- Perfect for lab environments and domain communication  

In this lab, **Adapter 2** on every VM uses:

- Mode: **Internal Network**
- Name: **intnet**

This allows:

- Domain controller ↔ Windows client communication  
- Linux web server ↔ database server communication  
- DHCP and DNS traffic inside the lab  

---

## 4. Why NAT + Internal Network

Using both adapters provides the best of both worlds:

| Purpose | NAT | Internal Network |
|--------|-----|------------------|
| Internet access | ✔ | ✘ |
| Lab isolation | ✘ | ✔ |
| Domain communication | ✘ | ✔ |
| Software updates | ✔ | ✘ |

This setup mirrors real enterprise networks where servers have:

- One interface for internal communication  
- One interface for external or upstream access  

---

## 5. Summary

Each VM in the lab uses:

- **Adapter 1: NAT**  
- **Adapter 2: Internal Network (intnet)**  

This ensures a stable, isolated, and realistic environment for Windows Server, Windows clients, and Linux servers.

---

## 6. Next Steps

Continue with:

**05-internal-network-setup.md**  
This explains how to configure the internal network and verify connectivity between all machines.
