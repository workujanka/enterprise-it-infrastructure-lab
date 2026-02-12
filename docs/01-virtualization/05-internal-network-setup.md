# 05 — Internal Network Setup

This section explains how to configure and verify the internal network used by all virtual machines in the enterprise IT infrastructure lab. The internal network allows Windows and Linux machines to communicate privately without exposing them to the host or the internet.

---

## 1. Create the Internal Network

1. Open VirtualBox
2. Go to **Tools** → **Network**
3. Select the **Host-only Networks** tab
4. Click **Create**
5. Name the network: **intnet**
6. Leave DHCP disabled

The internal network is now available for all VMs.

---

## 2. Attach VMs to the Internal Network

Each VM must have two network adapters:

- Adapter 1: NAT  
- Adapter 2: Internal Network (intnet)

To configure Adapter 2:

1. Select a VM  
2. Click **Settings**  
3. Go to **Network**  
4. Enable **Adapter 2**  
5. Set **Attached to:** Internal Network  
6. Set **Name:** intnet  
7. Click **OK**

Repeat for:

- WIN-DC01  
- WIN-CLIENT03  
- LNX-WEB01  
- LNX-DB01  

---

## 3. Verify Internal Network Connectivity

### 3.1 Check IP addresses

Inside each VM, run:

- **Windows:**  
  `ipconfig`

- **Linux:**  
  `ip a`

Each VM should receive an IP address from the domain controller once DHCP is configured later.  
Before DHCP is set up, VMs may show:

- No IP  
- A 169.254.x.x APIPA address  
- A manually assigned address (if configured)

This is normal at this stage.

---

## 4. Test Connectivity Between VMs

After all VMs are attached to **intnet**, test communication.

### 4.1 Ping between Windows and Linux

From WIN-DC01:

```
ping <IP-of-WIN-CLIENT03>
```

From LNX-WEB01:

```
ping <IP-of-LNX-DB01>
```

If DHCP is not yet configured, use temporary static IPs.

---

## 5. Assign Temporary Static IPs (Optional)

If you want to test connectivity before DHCP is configured:

### Windows

```
Control Panel → Network and Internet → Network Connections
Right-click Adapter → Properties → IPv4
Set:
IP: 192.168.10.x
Mask: 255.255.255.0
Gateway: (leave empty)
DNS: (leave empty)
```

### Linux

```
sudo nano /etc/netplan/00-installer-config.yaml
```

Example:

```
addresses: [192.168.10.x/24]
gateway4: null
nameservers: {}
```

Apply:

```
sudo netplan apply
```

---

## 6. Summary

The internal network is now configured and all VMs are connected to:

- NAT (internet access)
- Internal Network (intnet) for lab communication

This completes the virtualization setup phase.

---

## 7. Next Steps

Proceed to the Windows Server setup documentation to configure:

- Active Directory  
- DNS  
- DHCP  
- Domain join  
