# Acer Nitro 5 AN515-54 Monterey
 
 ![](https://visitor-badge.glitch.me/badge?page_id=itsmeshibintmz.Acer-Nitro-5-AN515-54-Monterey) 
 
 macOS Monterey on Acer Nitro 5 AN515-54 with OpenCore 0.7.5 EFI folder.

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

## Installation

### How To Install

- Format your USB "non-bootable" using RUFUS and delete any leftover in USB(autoruns).
- Create directory "EFI" in your EFI Partition (eg. Pendrive or Haarddrive).
- Clone this repo and paste contents of "EFI" directory (BOOT and OC) onto created directory.
- Create a director "com.apple.recovery.boot" in USB.
- Paste contents of "com.apple.recovery.boot" directory onto created directory.
- Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select Generate SMBIOS, as model sekect MacBookPro16,4.
- Open config.plist with [ProperTree](https://github.com/corpnewt/ProperTree) and go to platforminfo > Generic. Set MLB( Board Serial), SystemSerialNumber(Serial), and SystemUUID (SmUUID) to generate values.
- Boot it!.