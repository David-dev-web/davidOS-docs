# 🖥️ Welcome to DavidOS

DavidOS is an Ubuntu-based operating system that combines the stability and security of a modern Linux kernel with the classic, nostalgic aesthetic of Windows 95. It's the perfect system for anyone looking for a fast, reliable OS but who loves the iconic design of the 90s.

---

## 📥 Download DavidOS v1.0

<div style="text-align: center; margin: 30px 0;">
  <a href="https://github.com/David-dev-web/davidos-docs/releases/latest" class="download-btn">
    ⬇️ DOWNLOAD LATEST RELEASE
  </a>
</div>

*This will take you to the latest release on GitHub where you can download the necessary files.*

---

## ⚙️ IMPORTANT: How to Activate the Chicago95 Theme

After installing DavidOS, the system will initially have the default look. To unlock the full retro experience, please follow these simple steps.

### 📦 Step 1: Install the Theme

1. Open the **Terminal** (search for "Terminal" in Activities).
2. Enter the following commands one by one, pressing Enter after each:

```bash
git clone https://github.com/grassmunk/Chicago95.git
```

```bash
cd Chicago95 && ./install.sh
```

3. Follow the installer instructions. You can simply press **Enter** for most questions.

### 🔧 Step 2: Enable Shell Theming

1. In the Terminal, enter the following command (you'll need your password):

```bash
sudo apt install gnome-shell-extensions
```

2. **⚠️ Reboot your computer** - This is an important step!

### 🎨 Step 3: Activate the Theme

1. Open the **"Tweaks"** application (search for "Optimierungen" or "Tweaks").
2. Go to the **"Extensions"** tab and switch **"User themes"** to **ON**.
3. Go to the **"Appearance"** tab and select **`Chicago95`** for:
   - Applications
   - Cursor
   - Icons
   - Shell

**✨ Done!** Your desktop will now transform into the classic Windows 95 look. Enjoy DavidOS!

---

## 🙏 Credits & Acknowledgments

DavidOS wouldn't be possible without the amazing work of the open-source community:

<div class="credits-box">

### 🎨 **Chicago95 Theme**
The beautiful Windows 95 aesthetic is powered by **[Chicago95](https://github.com/grassmunk/Chicago95)** created by **[@grassmunk](https://github.com/grassmunk)**.

**License:** [GPL-3.0](https://github.com/grassmunk/Chicago95/blob/master/LICENSE)

A huge thank you to grassmunk and all contributors for keeping the retro dream alive! 🙌

</div>

### 🐧 Built On
- **Ubuntu** - Solid Linux foundation
- **GNOME/XFCE** - Desktop environment
- Various open-source tools and libraries

---

## 🚀 DavidOS Roadmap

This is a living document that outlines the future plans for DavidOS. Ideas and contributions are always welcome!

### ✅ Version 1.1 (Completed)
* ✔️ **Bug Fixes:** Addressed reported issues from initial release
* ✔️ **Pre-installed Applications:** Added curated, lightweight apps
* ✔️ **Theme Enhancements:** Integrated more icons and improved consistency

### 🔄 Version 2.0 (In Progress)
* [ ] **Custom Welcome Screen:** Develop a unique welcome application
* [ ] **System Update Tool:** Simple script for easy updates
* [ ] **Expanded Hardware Support:** Better compatibility

### 🌟 The Dream (Long-Term)
* [ ] **Unique Desktop Environment:** Move beyond a theme to custom DE
* [ ] **DavidOS App Store:** Simple software center for curated apps
* [ ] **Community Contributions:** Build a community around DavidOS

---

## 📜 License Information

DavidOS respects all upstream licenses:
- **Chicago95:** GPL-3.0 License
- **Ubuntu:** Various open-source licenses
- **DavidOS modifications:** Open for community use

---

## 💬 Get Involved

Want to contribute or report issues? Visit the [GitHub Repository](https://github.com/David-dev-web/davidOS-docs)

<div class="footer-box">
  <h3>🎉 Created with passion for the retro computing community</h3>
  <p>Bringing the nostalgia of Windows 95 to modern Linux</p>
</div>

---

<!-- DARK MODE SWITCHER CODE - START -->
<div id="theme-switch" class="theme-switcher">🌙 Dark Mode</div>
<script>
  function canStoreThemeChoice() {
    return localStorage.getItem('cookieConsent') === 'accepted';
  }

  window.applyThemeAfterConsent = function() {
    if (canStoreThemeChoice()) {
      const savedTheme = localStorage.getItem('theme');
      const body = document.body;
      const themeSwitch = document.getElementById('theme-switch');
      if (savedTheme === 'dark') {
        body.classList.add('dark-mode');
        if(themeSwitch) themeSwitch.textContent = '☀️ Light Mode';
      } else {
        body.classList.remove('dark-mode');
        if(themeSwitch) themeSwitch.textContent = '🌙 Dark Mode';
      }
    }
  }

  document.addEventListener('DOMContentLoaded', function() {
    const themeSwitch = document.getElementById('theme-switch');
    const body = document.body;

    function toggleTheme() {
      body.classList.toggle('dark-mode');
      const newTheme = body.classList.contains('dark-mode') ? 'dark' : 'light';
      
      if (body.classList.contains('dark-mode')) {
        themeSwitch.textContent = '☀️ Light Mode';
      } else {
        themeSwitch.textContent = '🌙 Dark Mode';
      }

      if (canStoreThemeChoice()) {
        localStorage.setItem('theme', newTheme);
      }
    }

    applyThemeAfterConsent();
    themeSwitch.addEventListener('click', toggleTheme);
  });
</script>
<!-- DARK MODE SWITCHER CODE - END -->

<!-- CODE FÜR COPY-BUTTONS - START -->
<script>
document.addEventListener('DOMContentLoaded', function() {
    const codeBlocks = document.querySelectorAll('pre');
    codeBlocks.forEach(block => {
        const button = document.createElement('button');
        button.innerText = '📋 Copy';
        button.className = 'copy-btn';
        block.style.position = 'relative';
        block.appendChild(button);
        
        button.addEventListener('click', () => {
            const code = block.querySelector('code').innerText;
            navigator.clipboard.writeText(code).then(() => {
                button.innerText = '✅ Copied!';
                button.classList.add('copied');
                setTimeout(() => { 
                    button.innerText = '📋 Copy';
                    button.classList.remove('copied');
                }, 2000);
            });
        });
    });
});
</script>
<!-- CODE FÜR COPY-BUTTONS - END -->

<!-- ECHTES COOKIE-BANNER (MODAL) - START -->
<div id="cookie-consent-modal" class="cc-overlay" style="display: none;">
  <div class="cc-modal">
    <h2>🍪 Your Privacy Matters</h2>
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
<script>
  document.addEventListener('DOMContentLoaded', function() {
    const modal = document.getElementById('cookie-consent-modal');
    const acceptBtn = document.getElementById('cc-btn-accept');
    const declineBtn = document.getElementById('cc-btn-decline');

    function hideModal() {
      modal.style.display = 'none';
    }

    if (!localStorage.getItem('cookieConsent')) {
      modal.style.display = 'flex';
    }

    acceptBtn.addEventListener('click', () => {
      localStorage.setItem('cookieConsent', 'accepted');
      hideModal();
      if (window.applyThemeAfterConsent) {
        window.applyThemeAfterConsent();
      }
    });

    declineBtn.addEventListener('click', () => {
      localStorage.setItem('cookieConsent', 'declined');
      localStorage.removeItem('theme');
      hideModal();
    });
  });
</script>
<!-- ECHTES COOKIE-BANNER (MODAL) - END -->

<audio id="startup-sound" src="https://raw.githubusercontent.com/David-dev-web/davidOS-docs/main/assets/css/windows95-startup.wav" preload="auto"></audio>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('startup-sound');
    const playSound = () => {
      audio.play().catch(() => {});
      document.removeEventListener('click', playSound);
    };
    document.addEventListener('click', playSound);
  });
</script>
