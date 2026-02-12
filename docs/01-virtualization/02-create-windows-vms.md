# 02 — Create Windows Virtual Machines (Windows Server + Windows Client)

This guide explains how to create the Windows Server and Windows Client virtual machines used in the enterprise IT infrastructure lab. All steps are performed using VirtualBox on macOS.

---

## 1. Requirements

Before creating the VMs, make sure you have:

- VirtualBox installed  
- Windows Server ISO (2019 or 2022)  
- Windows 10 or Windows 11 ISO  
- At least 16 GB RAM on your Mac  
- At least 60–80 GB free disk space  

### Download the Windows ISOs 

- **Windows Server 2019/2022:**  
  https://www.microsoft.com/en-us/evalcenter

- **Windows 10 ISO:**  
  https://www.microsoft.com/software-download/windows10

- **Windows 11 ISO:**  
  https://www.microsoft.com/software-download/windows11
 

---

## 2. Create the Windows Server VM (WIN-DC01)

### 2.1 Start the VM creation wizard

1. Open **VirtualBox**
2. Click **New**
3. Enter the following:

| Field | Value |
|-------|--------|
| Name | WIN-DC01 |
| Machine Folder | Default |
| Type | Microsoft Windows |
| Version | Windows 2019 (64-bit) or Windows 2022 (64-bit) |

Click **Continue**.

---

### 2.2 Assign memory

- Set **Memory Size** to **4096 MB** (4 GB) minimum  
- Recommended: **6144–8192 MB** if your Mac allows it  

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
| Size | 60 GB minimum (recommended: 80 GB) |

Click **Create**.

---

### 2.4 Attach the Windows Server ISO

1. Select **WIN-DC01** in the left panel  
2. Click **Settings**  
3. Go to **Storage**  
4. Under *Controller: IDE*, click the empty disk  
5. Click the small disk icon → **Choose a disk file**  
6. Select your Windows Server ISO  

Click **OK**.

---

### 2.5 Configure network settings

1. Open **Settings**  
2. Go to **Network**  
3. Adapter 1 → **NAT**  
4. Adapter 2 → **Internal Network**  
5. Name: **intnet**  

This allows:

- Internet access for updates  
- Internal communication with other lab machines  

Click **OK**.

---

### 2.6 Start the VM and install Windows Server

1. Select **WIN-DC01**  
2. Click **Start**  
3. Follow the Windows Server installation wizard:

- Install now  
- Standard Edition (Desktop Experience)  
- Custom installation  
- Select the virtual disk  
- Continue  

When installation completes, set:

- Administrator password  
- Basic settings  

Your domain controller VM is now ready for configuration in later steps.

---

## 3. Create the Windows Client VM (WIN-CLIENT03)

The process is similar to the server VM.

### 3.1 Start the VM creation wizard

1. Click **New**
2. Enter:

| Field | Value |
|-------|--------|
| Name | WIN-CLIENT03 |
| Type | Microsoft Windows |
| Version | Windows 10 (64-bit) or Windows 11 (64-bit) |

Click **Continue**.

---

### 3.2 Assign memory

- Set **Memory Size** to **4096 MB** (4 GB)  
- Recommended: **6144 MB** if available  

Click **Continue**.

---

### 3.3 Create the virtual hard disk

- Create a new VDI  
- Dynamically allocated  
- Size: **40–60 GB**  

Click **Create**.

---

### 3.4 Attach the Windows Client ISO

1. Open **Settings**  
2. Go to **Storage**  
3. Select the empty disk  
4. Choose your Windows 10/11 ISO  

Click **OK**.

---

### 3.5 Configure network settings

1. Go to **Network**  
2. Adapter 1 → **NAT**  
3. Adapter 2 → **Internal Network**  
4. Name: **intnet**  

Click **OK**.

---

### 3.6 Start the VM and install Windows

1. Select **WIN-CLIENT03**  
2. Click **Start**  
3. Install Windows normally  
4. Create a local user account  
5. Complete the setup  

This VM will later be joined to the domain created on WIN-DC01.

---

## 4. Summary

You now have two Windows VMs ready:

- **WIN-DC01** — Windows Server (future Domain Controller)  
- **WIN-CLIENT03** — Windows 10/11 client machine  

Both are configured with:

- NAT (internet access)  
- Internal Network (lab communication)  

---

## 5. Next Steps

Continue with:

**03-create-linux-vms.md**  
This will guide you through creating the Linux web and database servers for the lab.

