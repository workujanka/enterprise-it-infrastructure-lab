# 02 — Set Static IP Address

This section explains how to assign a static IP address to the Windows Server virtual machine. A fixed IP is required for Active Directory, DNS, and DHCP to function correctly.

---

## 1. Open Network Settings

1. Log in to **WIN-DC01**
2. Open **Control Panel**
3. Go to **Network and Internet**
4. Click **Network and Sharing Center**
5. Select **Change adapter settings**
6. Right‑click the **Internal Network** adapter
7. Choose **Properties**

---

## 2. Configure IPv4 Settings

1. Select **Internet Protocol Version 4 (TCP/IPv4)**
2. Click **Properties**
3. Choose **Use the following IP address**
4. Enter:

- IP address: **192.168.10.10**
- Subnet mask: **255.255.255.0**
- Default gateway: *(leave empty)*
- Preferred DNS server: *(leave empty)*

5. Click **OK**
6. Close all windows

---

## 3. Verify the Configuration

Open PowerShell and run:

```
ipconfig
```

You should see the static IP assigned to the internal network adapter.

---

## 4. Test Connectivity

Run:

```
ping 192.168.10.1
```

You should receive replies from the NAT gateway.

---

## 5. Summary

The server now has a static IP address on the internal network:

- **192.168.10.10/24**

This prepares the system for renaming and domain controller configuration.

---

## 6. Next Steps

Continue with:

**03-rename-server.md**
