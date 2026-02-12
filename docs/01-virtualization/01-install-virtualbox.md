# 01 — Install VirtualBox on macOS

This guide explains how to install Oracle VirtualBox on macOS to prepare your system for building the enterprise IT infrastructure lab. The steps are simple, beginner‑friendly, and follow a clean, repeatable workflow.

---

## 1. Download VirtualBox

1. Open your browser and go to the official VirtualBox website:  
   https://www.virtualbox.org

2. Select **Downloads** from the left menu.

3. Under *VirtualBox platform packages*, choose:  
   **macOS / Intel hosts**  
   or  
   **macOS / ARM64 (Apple Silicon)**  
   depending on your Mac hardware.

4. Save the `.dmg` installer to your Downloads folder.

---

## 2. Install VirtualBox

1. Open the downloaded `.dmg` file.
2. Double‑click **VirtualBox.pkg**.
3. If macOS warns you that the package is from an unidentified developer:
   - Open **System Settings**
   - Go to **Privacy & Security**
   - Scroll down and click **Allow** next to the VirtualBox installer
4. Run the installer again and follow the prompts:
   - Continue  
   - Agree  
   - Install  

5. Enter your macOS password when asked.

---

## 3. Approve System Extensions (macOS Security)

macOS may block VirtualBox kernel extensions.

If you see a message like *“System Extension Blocked”*:

1. Open **System Settings**
2. Go to **Privacy & Security**
3. Scroll down to the bottom
4. Click **Allow** next to Oracle America, Inc.
5. Restart your Mac if prompted

This step is required for VirtualBox networking and virtualization to work correctly.

---

## 4. Launch VirtualBox

After installation:

1. Open **Launchpad**
2. Search for **VirtualBox**
3. Open the application

You should now see the VirtualBox Manager interface with an empty VM list.

---

## 5. Verify Installation

Inside VirtualBox:

- Click **VirtualBox → About VirtualBox**  
- Confirm the version matches the one you downloaded  
- Check that the **New**, **Settings**, and **Start** buttons are active  

If everything looks correct, VirtualBox is ready for use.

---

## 6. Next Steps

Continue with the next documentation file:

**02-create-windows-vms.md**  
This will guide you through creating the Windows Server and Windows Client virtual machines used in the enterprise lab.

