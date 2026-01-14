# OpenCore EFI for Toshiba Portege Z30T-B (Ventura+) (STABLE)

## ⚠️ About TheDeusRa Repo:
(Updated OpenCore EFI) (Lost access to Original Account TheDeusRa)

<img width="1920" height="1080" alt="BG" src="https://github.com/user-attachments/assets/c1f5ae95-dca0-4c86-94ea-3dfc5db68bbc" />

This repository contains a complete OpenCore EFI configuration for the Toshiba Portege Z30T-B, optimized specifically for macOS Ventura and newer versions using OpenCore Legacy Patcher for graphics support
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

## 🚀 macOS Ventura & Newer Support

This EFI includes a specially tuned configuration file ensuring compatibility across versions

* **Ventura (macOS 13) and newer**
* Booting is handled by the same EFI
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

## 📥 Installation

1. Download the latest release from this repository
2. **Replace `AirportItlwm.kext**` with the version matching your target macOS (Monterey or Ventura)
3. Prepare a USB installer with macOS
4. Copy the `EFI` folder to the EFI partition of your USB drive
5. Boot from USB and perform the installation
6. After installation copy the EFI from USB to the EFI partition of the notebook drive
7. Run OCLP if you are on Ventura for graphics patching

Zde je aktualizovaná tabulka s přidaným ComboJackem

Pro tento model (Broadwell laptop) a obecně pro efektivní správu Hackintoshe bych doporučil doplnit tabulku o tyto nástroje, které jsou pro uživatele velmi praktické

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
