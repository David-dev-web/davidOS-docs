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

<style>
    /* --- GRUNDEINSTELLUNGEN (für Light & Dark Mode) --- */
    body {
        transition: background-color 0.3s, color 0.3s; /* Sanfter Übergang */
    }
    .wrapper {
        transition: background-color 0.3s, border-color 0.3s; /* Sanfter Übergang für den Kasten */
    }
    .theme-switcher {
        position: fixed;
        bottom: 20px;
        right: 20px;
        padding: 8px 12px;
        border-radius: 20px;
        cursor: pointer;
        font-size: 14px;
        z-index: 1000;
        font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji";
        transition: background-color 0.3s, color 0.3s;
    }

    /* --- LIGHT MODE (Standard) --- */
    .theme-switcher {
        background-color: #f0f0f0;
        color: #333;
        border: 1px solid #ddd;
    }

    /* --- DARK MODE REGELN --- */
    body.dark-mode {
        background-color: #0d1117; /* Dunkler GitHub-Hintergrund */
        color: #c9d1d9; /* Heller GitHub-Text */
    }
    body.dark-mode .wrapper {
        background-color: #161b22; /* Etwas hellerer Kasten-Hintergrund */
        border: 1px solid #30363d; /* Dezenter Rand für den Kasten */
        box-shadow: none;
    }
    body.dark-mode h1, body.dark-mode h2, body.dark-mode h3, body.dark-mode h4, body.dark-mode h5, body.dark-mode h6 {
        color: #58a6ff; /* Blau für Überschriften */
        border-bottom-color: #30363d; /* Passende Farbe für die Trennlinien */
    }
    body.dark-mode p, body.dark-mode li, body.dark-mode span {
        color: #c9d1d9; /* Stellt sicher, dass aller Fließtext hell ist */
    }
    body.dark-mode a {
        color: #58a6ff; /* Blau für Links */
        font-weight: bold; /* Macht Links etwas auffälliger */
    }
    body.dark-mode code {
        background-color: #313843; /* Dunklerer Hintergrund für Inline-Code */
    }
    body.dark-mode pre {
        background-color: #161b22; /* Hintergrund für Code-Blöcke, passend zum Kasten */
        border: 1px solid #30363d;
    }
    body.dark-mode hr {
        border-color: #30363d; /* Trennlinien-Farbe */
    }
    body.dark-mode .theme-switcher {
        background-color: #222;
        color: #fff;
        border: 1px solid #444;
    }
</style>



<div id="theme-switch" class="theme-switcher">
    🌙 Dark Mode
</div>

<script>
    (function() {
        const themeSwitch = document.getElementById('theme-switch');
        const body = document.body;

        function toggleTheme() {
            body.classList.toggle('dark-mode');
            if (body.classList.contains('dark-mode')) {
                localStorage.setItem('theme', 'dark');
                themeSwitch.textContent = '☀️ Light Mode';
            } else {
                localStorage.setItem('theme', 'light');
                themeSwitch.textContent = '🌙 Dark Mode';
            }
        }

        const currentTheme = localStorage.getItem('theme');
        if (currentTheme === 'dark') {
            body.classList.add('dark-mode');
            themeSwitch.textContent = '☀️ Light Mode';
        }

        themeSwitch.addEventListener('click', toggleTheme);
    })();
</script>
<!-- DARK MODE SWITCHER CODE - END -->



