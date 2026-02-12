# 04 — Basic Server Hardening

This section covers essential hardening steps to improve the security of the Windows Server before installing Active Directory and other roles. These steps follow standard best practices for a new server deployment.

---

## 1. Change the Administrator Password

1. Press **Ctrl + Alt + Delete**
2. Select **Change a password**
3. Enter a strong password with:

- Uppercase and lowercase letters  
- Numbers  
- Symbols  

---

## 2. Disable Unused Network Adapters

1. Open **Control Panel**
2. Go to **Network and Sharing Center**
3. Click **Change adapter settings**
4. Right‑click any unused adapters
5. Select **Disable**

Only the following should remain enabled:

- NAT adapter  
- Internal Network adapter  

---

## 3. Enable Windows Firewall

1. Open **Control Panel**
2. Go to **System and Security**
3. Select **Windows Defender Firewall**
4. Ensure the firewall is **On** for all profiles

---

## 4. Disable Remote Desktop (Optional)

If not needed at this stage:

1. Open **Server Manager**
2. Select **Local Server**
3. Find **Remote Desktop**
4. Set to **Disabled**

---

## 5. Install Windows Updates

1. Open **Settings**
2. Go to **Update & Security**
3. Click **Check for updates**
4. Install all available updates
5. Restart the server if required

---

## 6. Configure Time Synchronization

1. Open PowerShell as Administrator  
2. Run:

```
w32tm /config /manualpeerlist:"time.windows.com" /syncfromflags:manual /update
w32tm /resync
```

Correct time is required for Active Directory to function properly.

---

## 7. Summary

The server is now hardened with:

- Strong Administrator password  
- Only required network adapters enabled  
- Firewall active  
- Updates installed  
- Time synchronization configured  

This prepares the system for Active Directory installation.

---

## 8. Next Steps

Proceed to the Active Directory setup documentation.
