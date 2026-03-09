---
title: Remote Access From Anywhere
description: Learn how to access your UNO Q remotely from anywhere using Tailscale or RustDesk.
author: Arduino
tags: [UNO Q, remote access, ssh, tailscale, rustdesk]
---

# Remote Access from Anywhere

This tutorial covers how to access your [Arduino® UNO Q](https://store.arduino.cc/products/uno-q) remotely from outside your local network. We will cover two methods:

1. **Tailscale + SSH:** For secure command-line access.
2. **RustDesk:** For full graphical desktop access.

## 1. Tailscale + SSH

[Tailscale](https://tailscale.com/) is a zero-config VPN that creates a secure network between your devices. By installing Tailscale on your UNO Q and your computer, you can SSH into your board from anywhere as if it were on your local network.

### Installing Tailscale on UNO Q

1. Connect to your UNO Q via SSH or open a terminal in desktop mode.
2. Install Tailscale by running the following command:

   ```bash
   curl -fsSL https://tailscale.com/install.sh | sh
   ```

3. Authenticate and connect the board to your Tailscale network:

   ```bash
   sudo tailscale up
   ```

   *Follow the provided link to authenticate with your Tailscale account.*

### Connecting via SSH

Once both your computer and the UNO Q are connected to the same Tailscale network, you can find the board's Tailscale IP address in the Tailscale admin console or by running `tailscale ip -4` on the board.

From your computer, SSH into the board using its Tailscale IP:

```bash
ssh arduino@<tailscale-ip>
```

---

## 2. RustDesk (Desktop Access)

[RustDesk](https://rustdesk.com/) is an open-source remote desktop software. Since the UNO Q can be run headlessly (without a physical monitor), we will configure a dummy display driver so that the desktop environment loads and can be accessed remotely.

### 1. Install RustDesk

First, find the link for the latest `aarch64.deb` package on the [RustDesk Releases page](https://github.com/rustdesk/rustdesk/releases/latest). 

Connect to your board (via SSH or terminal) and download it using `wget`. Then, install it using a wildcard (`*`) so the command works regardless of the downloaded version:

```bash
wget <PASTE_DOWNLOAD_LINK_HERE>
sudo dpkg -i rustdesk-*-aarch64.deb
sudo apt -f install
```

### 2. Install and configure dummy display

Install the dummy display driver:

```bash
sudo apt install xserver-xorg-video-dummy
sudo mkdir -p /etc/X11/xorg.conf.d
```

Create the configuration file:

```bash
sudo tee /etc/X11/xorg.conf.d/10-dummy.conf << 'EOF'
Section "Device"
    Identifier "DummyDevice"
    Driver "dummy"
    VideoRam 256000
    Option "IgnoreEDID" "true"
EndSection

Section "Monitor"
    Identifier "DummyMonitor"
    HorizSync 28.0-80.0
    VertRefresh 48.0-75.0
    Modeline "1920x1080" 148.50 1920 2008 2052 2200 1080 1084 1089 1125
EndSection

Section "Screen"
    Identifier "DummyScreen"
    Device "DummyDevice"
    Monitor "DummyMonitor"
    DefaultDepth 24
    SubSection "Display"
        Depth 24
        Modes "1920x1080"
    EndSubSection
EndSection
EOF
```

### 3. Configure lightdm auto-login

Set up LightDM to automatically log in the `arduino` user (replace `arduino` with your username if it is different):

```bash
sudo tee -a /etc/lightdm/lightdm.conf << 'EOF'
[Seat:*]
autologin-user=arduino
EOF
```

### 4. Enable RustDesk and reboot

Enable the RustDesk service and reboot the board:

```bash
sudo systemctl enable rustdesk
sudo reboot
```

### 5. Set RustDesk password

After the board has rebooted, reconnect via SSH to retrieve your RustDesk ID and set a password:

```bash
rustdesk --get-id
rustdesk --password your_password
```

*Note down the ID — you'll need it to connect.*

### 6. Connect

Install RustDesk on your client device (macOS, iOS, Windows, Linux) from [rustdesk.com](https://rustdesk.com/). Enter the board's ID and password. This works across different networks from anywhere in the world.

### 7. Toggle between HDMI and headless mode

The dummy driver overrides the real GPU, meaning if you plug in a physical monitor via HDMI, it will show a black screen while the dummy driver is active. 

You can create a script to easily toggle between the dummy display and the physical HDMI output:

```bash
sudo tee /usr/local/bin/toggle-display << 'EOF'
#!/bin/bash
CONF="/etc/X11/xorg.conf.d/10-dummy.conf"
BAK="${CONF}.bak"

if [ -f "$CONF" ]; then
    mv "$CONF" "$BAK"
    echo "Switched to HDMI (physical display)"
else
    mv "$BAK" "$CONF"
    echo "Switched to dummy (headless/RustDesk)"
fi
systemctl restart lightdm
EOF

sudo chmod +x /usr/local/bin/toggle-display
```

Switch anytime by running:

```bash
sudo toggle-display
```

### After reboot

Everything starts automatically: LightDM auto-logs in on the dummy display, RustDesk runs, and the desktop is accessible remotely from any device.
