# Acer Nitro 5 AN515-54 Monterey
 
 ![](https://visitor-badge.glitch.me/badge?page_id=itsmeshibintmz.Acer-Nitro-5-AN515-54-Monterey) 
 
 macOS Monterey on Acer Nitro 5 AN515-54 with OpenCore 0.7.8 EFI folder.

 # Screesnshots

 <a href="https://github.com/itsmeshibintmz/Acer-Nitro-5-AN515-54-Monterey/blob/main/Screenshots/Screen%20Shot%202021-12-13%20at%201.41.37%20AM.png
"> <img src="Screenshots/Screen Shot 2021-12-13 at 1.41.37 AM.png" alt="dark mode"></a>

 <a href="https://github.com/itsmeshibintmz/Acer-Nitro-5-AN515-54-Monterey/blob/main/Screenshots/Screen%20Shot%202021-12-13%20at%204.12.37%20AM.png
"> <img src="Screenshots/Screen Shot 2021-12-13 at 4.12.37 AM.png" alt="dark mode"></a>

## Configuration

| Specifications      | Details                                            |
| ------------------- | -------------------------------------------------- |
| Laptop Model        | AN515-54 59CA                                      |
| Processor           | Intel® Core™ i5-9300H                              |
| Graphics            | Intel® UHD Graphics 630 & Nvidia GeForce® GTX 1650 |
| RAM                 | 16GB DDR4-2666Mhz                                  |
| Disk                | Micron 2200 1TBb PCIe® NVMe™ & 256 GB WDC SSD      |
| Audio               | Realtek HD Audio ALC255                            |
| Wifi                | Intel(R) Wireless-AC 9560 160MHz                   |
| Ethernet            | RealTek RTL8168/8111 PCI-E Gigabit Ethernet        |

## What's working

- [x] Audio (Input & Output)
- [x] iGPU
- [x] ACPI Display brightness
- [x] Ethernet
- [x] Sleep + Wake
- [x] Smart Touchpad + Gestures
- [x] WiFi (2.4Ghz and 5GHz)
- [x] Native hotkey support with Fn keys
- [x] iServices (Messages, FaceTime, etc.)

## What's not working

- [ ] GTX 1650 (macOS does not support recent Nvidia GPUs).
- [ ] HDMI port (since it's connected to the GTX 1650).

If you still want to use an external monitor, you can by a USB 3.0 to HDMI adapter.

The one I'm currently using is: https://www.amazon.in/dp/B013G4CJM8/?coliid=I21IXZ0W5ZAFHX&colid=IWBALZYIADBW&psc=0&ref_=lv_ov_lig_dp_it

## Installation

### How To Install

- Format your USB "non-bootable" using RUFUS and delete any leftover in USB(autoruns).
- Create directory "EFI" in your EFI Partition (eg. Pendrive or Haarddrive).
- Clone this repo and paste contents of "EFI" directory (BOOT and OC) onto created directory.
- Create a director "com.apple.recovery.boot" in USB.
- Paste contents of Basesystems files downloaded using Opencore onto created directory.
- Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select Generate SMBIOS, as model sekect MacBookPro16,4.
- Open config.plist with [ProperTree](https://github.com/corpnewt/ProperTree) and go to platforminfo > Generic. Set MLB( Board Serial), SystemSerialNumber(Serial), and SystemUUID (SmUUID) to generate values.
- Boot it!.

### First-time installation

- Set-up the BIOS configuration:
  - Boot to BIOS by pressing F2 during boot.
  - In the Main screen, enable F12 boot menu, disable Fast Boot, then press Ctrl+S and change the new SATA mode option to AHCI.
  - In the Boot screen, disable secure boot.
  - Finally, go to the Exit screen and select "Exit saving changes".
- Read through the following tutorial to create a bootable USB, and then place the EFI folder inside it:
   - https://dortania.github.io/OpenCore-Install-Guide/
- You should add Serial Number, UUID, MLB and ROM details to Config -> PlatformInfo -> Generic if you want to get iServices working as explained [here](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html).

### Post Install

- Clone the [ComboJack repo](https://github.com/hackintosh-stuff/ComboJack) and run the installer inside the `ComboJack_Installer` folder to get the jack port working correctly.
- Run the following commands for sleep wake:
  ```
  sudo pmset -a hibernatemode 0
  sudo pmset -a autopoweroff 0
  sudo pmset -a standby 0
  sudo pmset -a proximitywake 0
  ```
