# 03 — Create Linux Virtual Machines (Web + Database Servers)

This guide explains how to create the Linux virtual machines used in the enterprise IT infrastructure lab. These VMs will later serve as the web server (LNX-WEB01) and database server (LNX-DB01).

The steps are simple, GUI‑based, and follow the same structure as the Windows VM creation process.

---

## 1. Requirements

Before creating the Linux VMs, make sure you have:

- VirtualBox installed  
- A Linux ISO (recommended: Ubuntu Server 22.04 LTS)  
- At least 4 GB RAM available for each VM  
- At least 20–40 GB free disk space  

### Download Linux ISO 

- **Ubuntu Server 22.04 LTS:**  
  https://ubuntu.com/download/server

---

## 2. Create the Linux Web Server VM (LNX-WEB01)

### 2.1 Start the VM creation wizard

1. Open **VirtualBox**
2. Click **New**
3. Enter:

| Field | Value |
|-------|--------|
| Name | LNX-WEB01 |
| Type | Linux |
| Version | Ubuntu (64-bit) |

Click **Continue**.

---

### 2.2 Assign memory

- Set **Memory Size** to **2048–4096 MB**  
- Recommended: **4096 MB** for smoother performance  

Click **Continue**.

---

### 2.3 Create the virtual hard disk

- Choose **Create a virtual hard disk now**
- Click **Create**

Select:

| Setting | Value |
|---------|--------|
| Hard disk file type | VDI |
| Storage | Dynamically allocated |
| Size | 20–40 GB |

Click **Create**.

---

### 2.4 Attach the Linux ISO

1. Select **LNX-WEB01**
2. Click **Settings**
3. Go to **Storage**
4. Select the empty disk under *Controller: IDE*
5. Click the small disk icon → **Choose a disk file**
6. Select your Ubuntu Server ISO

Click **OK**.

---

### 2.5 Configure network settings

1. Open **Settings**
2. Go to **Network**
3. Adapter 1 → **NAT**
4. Adapter 2 → **Internal Network**
5. Name: **intnet**

Click **OK**.

---

### 2.6 Start the VM and install Ubuntu Server

1. Select **LNX-WEB01**
2. Click **Start**
3. Follow the Ubuntu Server installation steps:

- Choose language  
- Install Ubuntu Server  
- Use entire disk  
- Create a user  
- Skip optional snaps  
- Install OpenSSH server (recommended)  

When installation finishes, reboot the VM.

Your Linux web server is now ready for configuration.

---

## 3. Create the Linux Database Server VM (LNX-DB01)

The process is almost identical to LNX-WEB01.

### 3.1 Start the VM creation wizard

1. Click **New**
2. Enter:

| Field | Value |
|-------|--------|
| Name | LNX-DB01 |
| Type | Linux |
| Version | Ubuntu (64-bit) |

Click **Continue**.

---

### 3.2 Assign memory

- Set **Memory Size** to **2048–4096 MB**  
- Recommended: **4096 MB**  

Click **Continue**.

---

### 3.3 Create the virtual hard disk

- Create a new VDI  
- Dynamically allocated  
- Size: **20–40 GB**  

Click **Create**.

---

### 3.4 Attach the Linux ISO

1. Open **Settings**
2. Go to **Storage**
3. Select the empty disk
4. Choose your Ubuntu Server ISO

Click **OK**.

---

### 3.5 Configure network settings

1. Go to **Network**
2. Adapter 1 → **NAT**
3. Adapter 2 → **Internal Network**
4. Name: **intnet**

Click **OK**.

---

### 3.6 Start the VM and install Ubuntu Server

1. Select **LNX-DB01**
2. Click **Start**
3. Install Ubuntu Server the same way as LNX-WEB01

This VM will later host MySQL or PostgreSQL.

---

## 4. Summary

You now have two Linux VMs ready:

- **LNX-WEB01** — Web server (Apache/Nginx)  
- **LNX-DB01** — Database server (MySQL/PostgreSQL)  

Both are configured with:

- NAT (internet access)  
- Internal Network (lab communication)  

---

## 5. Next Steps

Continue with:

**04-networking-modes.md**  
This explains how VirtualBox networking works and why NAT + Internal Network is used in this lab.

