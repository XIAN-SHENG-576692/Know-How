# Gemini

How can I getting a USB device to pass through from physical machine (host) into an VirtualBox VM

You must provide URLs so I can understand where you obtained these methods from.

## Gemini

Getting a USB device to pass through to your VirtualBox VM can be a bit like trying to hand someone a physical object through a window—it requires the right "opening" and permissions.

To make this work, follow these specific steps.

---

## 1. Install the VirtualBox Extension Pack

By default, VirtualBox only supports USB 1.1. For **USB 2.0 and 3.0** support, you must install the **Oracle VM VirtualBox Extension Pack**.

- **Download:** Go to the [VirtualBox Downloads page](https://gemini.google.com/).
    
- **Version Match:** Ensure the Extension Pack version matches your installed VirtualBox version (e.g., if you have VirtualBox 7.0, get the 7.0 Extension Pack).
    
- **Installation:** Open VirtualBox, go to **File > Tools > Extension Pack Manager**, click **Install**, and select the downloaded file.
    

## 2. Linux Host Permissions (Crucial if you aren't on Windows)

If your **physical machine** runs Linux, VirtualBox won't have permission to access the USB hardware unless your user belongs to the `vboxusers` group.

1. Open a terminal.
    
2. Run the following command: `sudo usermod -aG vboxusers $USER`
    
3. **Log out and log back in** (or restart) for the change to take effect.
    

## 3. Configure the VM Settings

Before starting the VM, you need to "reserve" a spot for the USB device.

1. Select your VM and click **Settings**.
    
2. Go to the **USB** tab on the left.
    
3. Check **Enable USB Controller**.
    
4. Select **USB 2.0 (EHCI)** or **USB 3.0 (xHCI)** (usually 3.0 for modern devices).
    
5. Plug your USB device into the physical machine.
    
6. Click the **"Add Filter" icon** (the blue USB plug with a green plus sign) and select your device from the list. This creates a "Filter" so the VM automatically grabs that device whenever it's plugged in.
    

## 4. Attaching the Device Manually

If you don't want to set up a permanent filter, you can attach the device while the VM is running:

1. Start the VM.
    
2. In the VM window menu, go to **Devices > USB**.
    
3. Select the device you want to "pass through."
    
4. Wait a moment; the host will disconnect the device, and the guest OS will "discover" it.
    

---

### Sources for Reference:

- [Official VirtualBox Manual: USB Support](https://gemini.google.com/)
	- [3.11. USB Support](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/usb-support.html)
    
- [Ask Ubuntu: Setting up USB for VirtualBox](https://gemini.google.com/)
	- [How to set up USB for Virtualbox? - Ask Ubuntu](https://askubuntu.com/questions/25596/how-to-set-up-usb-for-virtualbox)
    
- [Adam the Automator: Enabling VirtualBox USB Passthrough](https://gemini.google.com/)
	- [Enabling VBox USB Passthrough to Access Devices](https://adamtheautomator.com/vbox-usb-passthrough/)
    

> **Pro Tip:** If the device appears "Busy" or won't attach, try unplugging it and plugging it back in _after_ the VM has fully booted to the desktop.