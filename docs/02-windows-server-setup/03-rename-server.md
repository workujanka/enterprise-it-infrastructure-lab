# 03 — Rename the Server

This section explains how to rename the Windows Server virtual machine before promoting it to a domain controller. A clear and consistent naming convention helps maintain an organized lab environment.

---

## 1. Open System Properties

1. Log in to the server  
2. Open **Server Manager**  
3. Select **Local Server**  
4. Click the current computer name next to **Computer name**

---

## 2. Change the Computer Name

1. In the System Properties window, click **Change**  
2. Enter the new name:

- **WIN-DC01**

3. Click **OK**  
4. Confirm the prompt to restart the server  
5. Click **Restart Now**

---

## 3. Verify the New Name

After the server restarts:

1. Log in  
2. Open **Server Manager**  
3. Confirm the computer name shows as **WIN-DC01**

You can also verify using PowerShell:

```
hostname
```

---

## 4. Summary

The server has been renamed to:

- **WIN-DC01**

This prepares the system for Active Directory installation and domain controller promotion.

---

## 5. Next Steps

Continue with:

**04-basic-hardening.md**
