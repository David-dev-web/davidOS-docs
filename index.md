---
layout: default
title: Welcome to DavidOS
nav_order: 1
---

DavidOS is an Ubuntu-based operating system that combines the stability and security of a modern Linux kernel with the classic, nostalgic aesthetic of Windows 95. It's the perfect system for anyone looking for a fast, reliable OS but who loves the iconic design of the 90s.

---

## Download DavidOS v1.0

[**CLICK HERE TO GO TO THE DOWNLOAD PAGE**](https://github.com/David-dev-web/davidos-docs/releases/latest )

*This will take you to the latest release on GitHub where you can download the necessary files.*

---

## IMPORTANT: How to activate the Chicago95 (Win95) Theme

After installing DavidOS, the system will initially have the default look. To unlock the full retro experience, please follow these simple steps.

### Step 1: Install the Theme

1.  Open the **Terminal** (search for "Terminal" in Activities).
2.  Enter the following two commands one by one, pressing Enter after each command. Click the copy icon on the right to copy the command.

    ```bash
    git clone https://github.com/grassmunk/Chicago95.git
    ```
    ```bash
    cd Chicago95 && python3 install.py
    ```
3.  Follow the instructions of the installer. You can simply press **Enter** for most questions.

### Step 2: Enable Shell Theming

1.  In the Terminal, enter the following command to install the necessary system extension. You will be asked for your password.

    ```bash
    sudo apt install gnome-shell-extensions
    ```
2.  **Reboot your computer.** This is an important step!

### Step 3: Activate the Theme

1.  Open the **"Tweaks"** application (search for "Optimierungen" or "Tweaks"  ).
2.  Go to the **"Extensions"** tab and switch **"User themes"** to **ON**.
3.  Go to the **"Appearance"** tab. Now, select **`Chicago95`** from the dropdown menu for the following four items:
    *   Applications
    *   Cursor
    *   Icons
    *   Shell

**Done!** Your desktop will now transform into the classic Windows 95 look. Enjoy DavidOS!

{% include banner.html %}


