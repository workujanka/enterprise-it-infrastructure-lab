# 01 — Install Windows Server

This section explains how to install Windows Server on the WIN-DC01 virtual machine. The installation prepares the system for configuring Active Directory, DNS, and DHCP in later steps.

---

## 1. Start the WIN-DC01 VM

1. Open VirtualBox  
2. Select **WIN-DC01**  
3. Click **Start**  
4. The VM will boot from the attached Windows Server ISO

---

## 2. Begin the Installation

1. Choose your language and keyboard layout  
2. Click **Install now**  
3. Select the edition:

- Windows Server 2019 Standard (Desktop Experience)  
or  
- Windows Server 2022 Standard (Desktop Experience)

4. Accept the license terms  
5. Choose **Custom: Install Windows only**  
6. Select the virtual hard disk  
7. Click **Next**

Windows Server will begin installing and restart automatically.

---

## 3. Set the Administrator Password

After installation:

1. Enter a strong password for the **Administrator** account  
2. Press **Finish**  
3. Log in using:

- Username: **Administrator**  
- Password: the one you created

---

## 4. Initial Configuration

### 4.1 Set the server name

1. Open **Server Manager**  
2. Click **Local Server**  
3. Click the computer name  
4. Click **Change**  
5. Set:

- Computer name: **WIN-DC01**

6. Restart the server

---

### 4.2 Configure the network adapter

1. Open **Network & Internet Settings**  
2. Select the **Internal Network** adapter  
3. Open **Properties**  
4. Select **IPv4**  
5. Set a static IP:

- IP address: **192.168.10.10**  
- Subnet mask: **255.255.255.0**  
- Gateway: leave empty  
- DNS: leave empty (DNS will be installed later)

Click **OK**.

---

## 5. Verify Connectivity

Open PowerShell and run:

```
ping 192.168.10.1
```

You should receive replies from the NAT gateway.

---

## 6. Summary

Windows Server is now installed and configured with:

- Administrator account  
- Server name: WIN-DC01  
- Static IP on the internal network  
- Basic connectivity  

The system is ready for Active Directory Domain Services.

---

## 7. Next Steps

Continue with:

**02-configure-active-directory.md**  
This will guide you through promoting WIN-DC01 to a domain controller.
