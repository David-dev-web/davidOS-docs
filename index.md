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

1.  Open the **"Tweaks"** application (search for "Optimierungen" or "Tweaks" ).
2.  Go to the **"Extensions"** tab and switch **"User themes"** to **ON**.
3.  Go to the **"Appearance"** tab. Now, select **`Chicago95`** from the dropdown menu for the following four items:
    *   Applications
    *   Cursor
    *   Icons
    *   Shell

**Done!** Your desktop will now transform into the classic Windows 95 look. Enjoy DavidOS!


<!-- ======================================================================================================================= -->
<!-- ============================================= START OF ALL CUSTOM CODE ================================================ -->
<!-- ======================================================================================================================= -->

<!-- DARK MODE SWITCHER STYLES -->
<style>
    /* --- GRUNDEINSTELLUNGEN (für Light & Dark Mode) --- */
    body {
        transition: background-color 0.3s, color 0.3s;
    }
    .wrapper {
        transition: background-color 0.3s, border-color 0.3s;
    }
    .theme-switcher {
        position: fixed; bottom: 20px; right: 20px;
        padding: 8px 12px; border-radius: 20px; cursor: pointer;
        font-size: 14px; z-index: 1000;
        font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji";
        transition: background-color 0.3s, color 0.3s;
    }
    .theme-switcher {
        background-color: #f0f0f0; color: #333; border: 1px solid #ddd;
    }
    body.dark-mode {
        background-color: #0d1117; color: #c9d1d9;
    }
    body.dark-mode .wrapper {
        background-color: #161b22; border: 1px solid #30363d; box-shadow: none;
    }
    body.dark-mode h1, body.dark-mode h2, body.dark-mode h3, body.dark-mode h4, body.dark-mode h5, body.dark-mode h6 {
        color: #58a6ff; border-bottom-color: #30363d;
    }
    body.dark-mode p, body.dark-mode li, body.dark-mode span {
        color: #c9d1d9;
    }
    body.dark-mode a {
        color: #58a6ff; font-weight: bold;
    }
    body.dark-mode code {
        background-color: #313843;
    }
    body.dark-mode pre {
        background-color: #161b22; border: 1px solid #30363d;
    }
    body.dark-mode hr {
        border-color: #30363d;
    }
    body.dark-mode .theme-switcher {
        background-color: #222; color: #fff; border: 1px solid #444;
    }
</style>

<!-- DARK MODE SWITCHER HTML -->
<div id="theme-switch" class="theme-switcher">
    🌙 Dark Mode
</div>

<!-- DARK MODE SWITCHER SCRIPT -->
<script>
    (function() {
        const themeSwitch = document.getElementById('theme-switch');
        const body = document.body;

        // Diese Funktion wird jetzt von zwei Stellen aufgerufen
        function applyInitialTheme() {
            // Prüft, ob die Zustimmung zum Speichern gegeben wurde
            if (window.canStoreThemeChoice && window.canStoreThemeChoice()) {
                const currentTheme = localStorage.getItem('theme');
                if (currentTheme === 'dark') {
                    body.classList.add('dark-mode');
                    themeSwitch.textContent = '☀️ Light Mode';
                }
            }
        }

        // Wir machen die Funktion global verfügbar, damit das Cookie-Banner sie finden kann
        window.applyThemeAfterConsent = applyInitialTheme;

        function toggleTheme() {
            body.classList.toggle('dark-mode');
            const isDarkMode = body.classList.contains('dark-mode');
            
            if (window.canStoreThemeChoice && window.canStoreThemeChoice()) {
                localStorage.setItem('theme', isDarkMode ? 'dark' : 'light');
            }
            
            themeSwitch.textContent = isDarkMode ? '☀️ Light Mode' : '🌙 Dark Mode';
        }

        // Führe die Funktion beim ersten Laden der Seite aus
        applyInitialTheme();

        themeSwitch.addEventListener('click', toggleTheme);
    })();
</script>

<!-- COPY-BUTTONS SCRIPT -->
<script>
function addCopyButtons() {
    const codeBlocks = document.querySelectorAll('pre');
    codeBlocks.forEach(block => {
        const button = document.createElement('button');
        button.innerText = 'Copy';
        button.style.position = 'absolute';
        button.style.top = '5px';
        button.style.right = '5px';
        button.style.padding = '5px 8px';
        button.style.fontSize = '12px';
        button.style.backgroundColor = '#333';
        button.style.color = 'white';
        button.style.border = '1px solid #555';
        button.style.borderRadius = '4px';
        button.style.cursor = 'pointer';
        button.style.opacity = '0.7';
        block.style.position = 'relative';
        block.appendChild(button);
        button.addEventListener('click', () => {
            const code = block.querySelector('code').innerText;
            navigator.clipboard.writeText(code).then(() => {
                button.innerText = 'Copied!';
                setTimeout(() => { button.innerText = 'Copy'; }, 2000);
            });
        });
    });
}
window.addEventListener('load', addCopyButtons);
</script>

<!-- COOKIE CONSENT MODAL STYLES -->
<style>
  .cc-overlay {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    z-index: 2999; display: flex; justify-content: center; align-items: center;
  }
  .cc-modal {
    background-color: #161b22; color: #c9d1d9; padding: 25px 30px;
    border-radius: 8px; border: 1px solid #30363d;
    box-shadow: 0 5px 20px rgba(0,0,0,0.4);
    max-width: 550px; width: 90%; text-align: left;
  }
  .cc-modal h2 { color: #58a6ff; margin-top: 0; }
  .cc-modal p { color: #c9d1d9 !important; line-height: 1.6; }
  .cc-modal code { background-color: #313843; padding: 2px 4px; border-radius: 3px; }
  .cc-buttons { margin-top: 20px; display: flex; justify-content: flex-end; gap: 10px; }
  .cc-btn {
    border: none; padding: 10px 20px; border-radius: 5px;
    cursor: pointer; font-weight: bold; font-size: 14px;
  }
  .cc-btn-accept { background-color: #58a6ff; color: #fff; }
  .cc-btn-decline { background-color: #444; color: #eee; }
</style>

<!-- COOKIE CONSENT MODAL HTML -->
<div id="cookie-consent-modal" class="cc-overlay" style="display: none;">
  <div class="cc-modal">
    <h2>Your Privacy Matters</h2>
    <p>
      This website uses your browser's <code>localStorage</code> to enhance your experience by remembering your theme choice (Light/Dark Mode).
    </p>
    <p>
      By clicking <b>"Accept"</b>, you consent to this storage. If you <b>"Decline"</b>, your choice will not be saved, and the site will load with the default theme on each visit.
    </p>
    <div class="cc-buttons">
      <button id="cc-btn-decline" class="cc-btn cc-btn-decline">Decline</button>
      <button id="cc-btn-accept" class="cc-btn cc-btn-accept">Accept</button>
    </div>
  </div>
</div>

<!-- COOKIE CONSENT MODAL SCRIPT -->
<script>
  // Diese Funktion wird global gebraucht, damit der Dark-Mode-Switcher sie aufrufen kann
  function canStoreThemeChoice() {
    return localStorage.getItem('cookieConsent') === 'accepted';
  }

  // Initialisierungslogik für das Banner
  (function() {
    const modal = document.getElementById('cookie-consent-modal');
    const acceptBtn = document.getElementById('cc-btn-accept');
    const declineBtn = document.getElementById('cc-btn-decline');

    function hideModal() {
      modal.style.display = 'none';
    }

    // Nur anzeigen, wenn noch keine Entscheidung getroffen wurde
    if (!localStorage.getItem('cookieConsent')) {
      modal.style.display = 'flex';
    }

    acceptBtn.addEventListener('click', () => {
      localStorage.setItem('cookieConsent', 'accepted');
      hideModal();
      // Signal an den Dark-Mode-Code senden, dass er sich aktualisieren soll
      if (window.applyThemeAfterConsent) {
        window.applyThemeAfterConsent();
      }
    });

    declineBtn.addEventListener('click', () => {
      localStorage.setItem('cookieConsent', 'declined');
      // Alte Theme-Einstellungen löschen, falls vorhanden
      localStorage.removeItem('theme');
      hideModal();
    });
  })();
</script>
