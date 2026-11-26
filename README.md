<div align="right">
  <a href="README_AR.md">
    <img src="https://img.shields.io/badge/🌍_Read_in_Arabic-0A84FF?style=for-the-badge" alt="Read in Arabic" />
  </a>
</div>

# 🪟 UnattendBuilder — Windows 10/11 Unattended Setup & Ventoy Auto-Install Builder

<div align="center">
  <a href="https://github.com/Esam-Haraz/UnattendBuilder/releases/latest/download/UnattendBuilder.exe">
    <img src="https://img.shields.io/badge/⬇_Download_Latest-UnattendBuilder.exe-2ea44f?style=for-the-badge&logo=windows" alt="Download UnattendBuilder" />
  </a>
</div>

**UnattendBuilder** is a standalone, zero-dependency Windows desktop application for generating clean, validated **`autounattend.xml`** answer files for **Windows 10 & Windows 11**, paired with one-click **Ventoy USB Auto-Installation** integration.

Instead of manually clicking through Windows Setup screens, bypassing hardware checks, skipping Microsoft Account prompts, configuring privacy settings, tweaking File Explorer/Taskbar, and uninstalling dozens of pre-installed bloatware apps after every format, **UnattendBuilder** lets you configure all 16 setup stages visually—with a clear explanation under every option—and apply the resulting `autounattend.xml` directly to your **Ventoy** flash drive.

---

## ⚙️ How UnattendBuilder Works

1. **Configure Your Ideal Windows Image:** Choose your Target OS (`Windows 11` or `Windows 10`) and walk through the 16 organized sections—every option includes a plain-language description underneath explaining exactly what it does.
2. **Portable Profile Persistence:** Your choices are saved alongside the executable in `UnattendBuilder Profile.json` so you can tweak and regenerate `autounattend.xml` anytime.
3. **Export & Apply Straight to Ventoy USB:** Click **Export autounattend.xml...** to save your answer file, then either:
   - **Apply directly to your Ventoy USB in one click** (auto-detects your USB drive & Windows `.iso` files, copies `autounattend.xml` to `/ventoy/autounattend.xml`, and safely updates `/ventoy/ventoy.json` while backing up any existing config to `ventoy.json.bak`), or
   - Follow the built-in **VentoyPlugson** step-by-step guide / copy the ready-made `ventoy.json` snippet.

---

## ✨ Key Features

* **Bilingual Interface (English & Arabic RTL):** Defaults to English with instant live switching to full Arabic (`عربي` / `English`), persisted automatically in `ui_settings.json`.
* **Native Windows 11 Dark & Light Themes:** Resizable native Windows 11 window frame with **Dark Slate** and **Light Mode**, including synchronized native title bar coloring.
* **Clear Explanation Under Every Option:** No cryptic XML tags or guesswork—every checkbox, dropdown, visual effect, and bloatware item explains its exact effect on Windows.
* **Context-Aware Warnings:** Compatibility and security warnings appear only inside their relevant section tab (e.g., Windows Defender, UAC/Windows Update/Smart App Control, Microsoft Store/Winget).
* **Safe Disk Handling by Design:** Disk selection and partitioning remain 100% interactive during Windows Setup—UnattendBuilder never wipes or auto-partitions any drive.
* **Built-in XML Preview & Validation:** Inspect the exact UTF-8 `autounattend.xml` before exporting, with live validation for computer names, local usernames, and product keys.

---

## 📋 All 16 Configuration Sections

| # | Section | What It Configures |
| :---: | :--- | :--- |
| **1** | **Region & Language** | Windows UI language, User Locale, Home Location (GeoId), Setup UI language (with automatic dynamic Setup keyboard layout), and ordered input keyboard layouts. |
| **2** | **Disk & Partition** | Kept intentionally interactive during Windows Setup so you safely pick the exact drive/partition on every PC. |
| **3** | **Bypass Win11 Checks** | `LabConfig` registry bypasses for TPM 2.0, Secure Boot, 4 GB RAM, unsupported CPUs, and 64 GB storage (automatically disabled when targeting Windows 10). |
| **4** | **Windows Defender** | Optional disable of Windows Defender services (`Start = 4`) during `specialize` (off by default, with clear security warning). |
| **5** | **Windows Edition** | Auto-detect firmware BIOS/UEFI key, select any Windows 10/11 edition via Microsoft generic install keys (selection only, does not activate), or enter a custom 25-character key. |
| **6** | **Computer Name** | Windows default (`DESKTOP-XXXXXXX`), random (`*`), or validated custom NetBIOS computer name. |
| **7** | **Time Zone** | Standard Windows time zones (`tzutil /l`) applied automatically during `specialize`. |
| **8** | **User Accounts** | Offline local Windows accounts (Administrators/Users), skips Microsoft Account OOBE requirement, and optional Auto-Logon with boot count. |
| **9** | **File Explorer** | Hidden/system files visibility, always show file extensions, open to `This PC`, and Windows 11 taskbar `End task` right-click option. |
| **10** | **Start & Taskbar** | Search box style, disable Widgets/News, left-aligned taskbar (Win11), hide Task View, and disable Bing web search in Start. |
| **11** | **System Tweaks** | Windows Update policy, UAC, Smart App Control, SmartScreen, Fast Startup, System Restore, BitLocker auto-encryption prevention, Edge tweaks, mouse acceleration, and empty `Windows.old` cleanup. |
| **12** | **Visual Effects** | Windows Default, Best Appearance, Best Performance, or Custom toggle for all 17 Windows Performance visual effects. |
| **13** | **Desktop Icons** | Show `This PC`, `User's Files`, `Network`, `Recycle Bin`, and `Control Panel` on the desktop automatically. |
| **14** | **Express Settings** | Pre-answer all OOBE privacy screens (Disable all tracking/telemetry, Windows default, or custom per-setting toggles). |
| **15** | **Sticky Keys** | Keep default, disable the 5x Shift popup (`Flags = 506`), or specify custom flags. |
| **16** | **Remove Bloatware** | Searchable grid of 59 pre-installed Windows apps, capabilities, and optional features (Copilot, Recall, OneDrive, Teams, Xbox, Clipchamp, Widgets, etc.) with Win11-only auto-filtering. |

---

## 💾 Using `autounattend.xml` with Ventoy

### Option A — Direct One-Click Apply (Built into UnattendBuilder)
1. Plug in your **Ventoy** USB flash drive and click **Export autounattend.xml...** (or click **💾 Ventoy USB** in the top bar).
2. Select your Ventoy drive (auto-detected) and pick your Windows `.iso` file from the scanned list.
3. Click **⚡ Copy XML & Configure Ventoy USB Now** — UnattendBuilder copies `/ventoy/autounattend.xml`, backs up any existing `/ventoy/ventoy.json` to `ventoy.json.bak`, and merges the `auto_install` entry without touching your other Ventoy plugins.

### Option B — Manual Setup via `VentoyPlugson`
1. Copy `autounattend.xml` to `/ventoy/autounattend.xml` on your Ventoy USB drive.
2. Run `VentoyPlugson.exe`, select your Ventoy USB drive, and click **Start**.
3. Open **Auto Installation Plugin** → click **Add** → enter your ISO path (e.g. `/Win11.iso`) and template path (`/ventoy/autounattend.xml`) → click **OK**.

---

## 📄 Author & License
Developed by **Essam** — Copyright © 2026 Essam. All rights reserved.  
Contact / Portfolio: [esam-haraz.github.io/hub](https://esam-haraz.github.io/hub/#contact)
