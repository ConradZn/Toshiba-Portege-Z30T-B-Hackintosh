# OpenCore EFI for Toshiba Portege Z30T-B (Ventura+)

<img width="1920" height="1080" alt="Pink Black Gradient Motivational Desktop Wallpaper " src="https://github.com/user-attachments/assets/23c84d72-d084-42f8-8a81-829188b1a12a" />

This repository contains a complete OpenCore EFI configuration for the Toshiba Portege Z30T-B, optimized specifically for macOS Ventura, Sonoma and macOS Sequoia using OpenCore Legacy Patcher for graphics support
---

## 💻 Hardware Specifications

| Component | Specification | Status |
| --- | --- | --- |
| **CPU** | Intel Core i5/i7 (Broadwell) 5th Gen | ✅ Working |
| **GPU** | Intel HD Graphics 5500 | ✅ Working (see notes) |
| **RAM** | DDR3L 1600MHz 8GB | ✅ Working |
| **Display** | 13.3" Display | ✅ Working |
| **Audio** | Realtek ALC255 | ✅ Working |
| **Ethernet** | Intel I218-LM | ✅ Working |
| **Wi-Fi/BT** | Intel Wireless-AC 7265 | ✅ Working (with AirportItlwm) |
| **Trackpad** | ALPS / Synaptics | ✅ Working (VoodooPS2) |

<img width="1600" height="900" alt="Snímek obrazovky 2026-01-16 v 8 11 35" src="https://github.com/user-attachments/assets/4656535a-a0ce-4015-af61-c67a7c1252c5" />

## 🚀 macOS Ventura & Newer Support

This EFI includes a specially tuned configuration file ensuring compatibility across versions

* **Ventura (macOS 13) and newer**
* **Important:** For full graphics acceleration on Broadwell (HD 5500) in Ventura, you must use **OpenCore Legacy Patcher (OCLP)** post-install
* **[Download OCLP Here](https://github.com/dortania/OpenCore-Legacy-Patcher/releases)**
* Kexts are configured not to block booting of newer systems

---

## ⚙️ BIOS Settings

Before installation ensure your BIOS is set as follows

* **Secure Boot:** Disabled
* **VT-d:** Disabled (or use DisableIoMapper in config)
* **Fast Boot:** Disabled
* **CSM:** Disabled (UEFI and UEFI Legacy only)
* **SATA Mode:** AHCI (Automatic)

**⚠️ Mandatory Installation Steps**

* **SMBIOS Generation:** You **must generate** your own unique serial numbers (Serial, Board Serial, UUID) for model **MacBookPro14,1** using GenSMBIOS before booting to ensure iServices work and to avoid conflicts, **MacBookPro16,2** for Sequoia.
* **Graphics:** Post-install patching using **OpenCore Legacy Patcher** is required to enable Intel HD 5500 graphics acceleration

## 🐛 Known Issues

* **macOS Sonoma/Sequoia (macOS 14/15)**
* **iServices:** iMessage and FaceTime are currently **broken/not working** on Sequoia due to changes in the OS structure and root patching
* iCloud Drive, App Store and other Apple ID services work fine
* Everything else (Graphics, Audio, WiFi) works stable  
  --
  * **Ventura (macOS 12)**
  * All iServices work correctly with valid SMBIOS

## 📥 Installation

1. Download the latest release from this repository
2. **Generate SMBIOS:** Use GenSMBIOS to generate new Serial, Board Serial and UUID for **MacBookPro14,1** / **MacBookPro16,2**
3. Prepare a USB installer with macOS
4. Copy the `EFI` folder to the EFI partition of your USB drive
5. Boot from USB and perform the installation
6. **Disable SIP:** After install, boot into Recovery, open Terminal and run `csrutil disable` followed by `csrutil authenticated-root disable`, then restart
7. **Run OCLP** immediately to patch graphics

## 🛠 Recommended Utilities

| Utility | Description | Download |
| --- | --- | --- |
| **Discrete Scroll** | Fixes scroll wheel acceleration and behavior for external mice on macOS | [GitHub Link](https://github.com/emreyolcu/discrete-scroll) |
| **ComboJack** | Enables proper headset detection and popup menu for the combo audio jack | [GitHub Link](https://github.com/hoaug-tran/ComboJack) |
| **Hackintool** | The swiss army knife for Hackintosh (diagnostics, USB mapping, kext checks) | [GitHub Link](https://github.com/benbaker76/Hackintool) |
| **Stats** | Open source system monitor in menu bar (CPU, GPU, Battery, Sensors) | [GitHub Link](https://github.com/exelban/stats) |
| **Rectangle** | Move and resize windows in macOS using keyboard shortcuts or snap areas | [GitHub Link](https://github.com/rxhanson/Rectangle) |
| **ProperTree** | The best lightweight plist editor for OpenCore config files | [GitHub Link](https://github.com/corpnewt/ProperTree) |

## 🙌 Credits

- [acidanthera](https://github.com/acidanthera) for OpenCore and kexts  
- [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel Wi-Fi/BT support  
- [Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/) for thorough documentation  
- [hackintosh-stuff/ComboJack](https://github.com/hackintosh-stuff/ComboJack) for audio jack support  
- Inspired by [yusufklncc/Toshiba-Portege-Z30-Hackintosh](https://github.com/yusufklncc/Toshiba-Portege-Z30-Hackintosh)
