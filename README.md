
🇬🇧 README — EFI for Lenovo IdeaPad Slim 3 16ABR8 (macOS Monterey only)

> 📌 This is the English version of the README.

>🇷🇺 Русская версия доступна здесь: [README_RU.md](README_RU.MD)



This EFI is intended only for macOS Monterey.
While macOS Big Sur installation is technically possible, this EFI is specifically configured and tested for Monterey.


---

💻 Laptop specifications:

Model: Lenovo IdeaPad Slim 3 16ABR8

CPU: AMD Ryzen 7 7730U (Zen 2)

Graphics: AMD Radeon Vega 8

Audio: Realtek ALC257 ✅

Camera: Built-in ✅

Wi-Fi / Bluetooth: MediaTek MT7921 ❌

Bootloader: OpenCore 1.0.5

Supported macOS: macOS Monterey (12.x)



---

🧩 Included SSDTs:

SSDT-EC

SSDT-PLUG-ALT

SSDT-USBX

SSDT-XOSI



---

✅ What works:

Full hardware graphics acceleration (Vega 8)

Audio (via alcid=11)

Built-in camera

USB ports (configured via SSDT-USBX)

Smooth interface and animations

Stable installation and boot process



---

⚠️ What does not work:

❌ Wi-Fi and Bluetooth are not supported — MediaTek MT7921 is not macOS-compatible

🔌 Internet access is available only via USB tethering from a phone
The required HoRNDIS.kext is already included in this EFI

🔅 Brightness hotkeys might not work yet (currently being addressed)

🖥️ On the initial setup of macOS Monterey, you may see a welcome screen with white side borders — this is normal behavior, not a bug



---

⚙️ Boot arguments (NVRAM boot-args):
```
-v debug=0x100 keepsyms=1 npci=0x2000 -cdfon -vi2c-force-polling amfi_get_out_of_my_way=1 acpi_layer=1 alcid=11
```

---

📁 EFI structure:
```
EFI
├── BOOT
│   └── BOOTx64.efi
└── OC
  ├── ACPI
  ├── Drivers
  ├── Kexts
  ├── Tools
  ├── config.plist
  └── OpenCore.efi
