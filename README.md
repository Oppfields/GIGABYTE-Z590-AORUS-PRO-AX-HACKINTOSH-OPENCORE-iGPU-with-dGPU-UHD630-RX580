# GIGABYTE-Z590-AORUS-PRO-AX-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580

Opencore Hackintosh settings for Gigabyte Z590 AORUS PRO AX (rev. 1.0)

10/09/22 – WIP the build boots into the macOS installer but fails 15 mins into the process. This document will track the build process and document changes. The target OS is macOS Big Sur.

Note: this build follows [dhckdgjs](https://github.com/dhckdgjs/GIGABYTE-Z590-VISION-G-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580/blob/main/README.md) Z590 guide but is specifically focused on the GIGABYTE Z590 AORUS PRO AX motherboard.

## Components

- GIGABYTE Z590 AORUS PRO AX (rev, 1.0, BIOS F8 with ALC4080 and i225-V)
- Intel® Core™ i5-10600K 4.10GHz (Comet Lake, FCLGA1200)
- Corsair CMK16GX4M2B3200C16 Vengeance LPX 16 GB (4 x 8 GB)
- Noctua NH-L12S, Premium Low Profile CPU Cooler with Quiet 120mm PWM Fan

## Components: Already owned

- Gigabyte Radeon RX 580 Gaming 8G
- Samsung SSD 840 Pro, 128Gb
- Corsair CX600M, ATX power supply
- HD (1920x1080) DVI, HDMI Monitor
- Custom open frame case for rack mount
- ARCTIC P8 80mm case Fan (x1)
- ARCTIC P12 120mm case Fan (x3)
- USB keyboard + Mouse

## Caution

BIOS F8, Major vulnerabilities updates, customers are strongly encouraged to update to this release at the earliest.

Note from [dhckdgjs](https://github.com/dhckdgjs/GIGABYTE-Z590-VISION-G-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580/blob/main/README.md): GIGABYTE Z590 Vision-G M/B(BIOS F2) CAN NOT BOOT with GIGABYTE RX580 MINING or GAMING. (Compatibility issue)

## Comments

- [OpenCore](https://github.com/acidanthera/OpenCorePkg) 0.8.4

## BIOS
 
1. Switch to BIOS (DEL)
2. Check BIOS Ver (F8 or above)
3. Load the Optimised Defaults (F7)
4. Switch to Advanced Mode (F2)

### Favorites (F11)

No change

### Tweaker

No change

### Settings

Platform Power

IO Ports

* Above 4G Decoding (Disabled)
	* 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some Z490 and newer motherboards. Please ensure that Booter -> Quirks -> ResizeAppleGpuBars is set to 0 if this is enabled.
	* Disable in BIOS and config.plist ResizeAppleGpuBars = -1

Miscellaneous

### System Info

No change

### Boot

* CFG Lock (Disabled)
	* CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)

* Fast Boot (Disable Link)

* Windows 10 Features (Windows 10)

* CMS Support (Disabled)
	* Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)

## Procedure

OpenCore Install Guide:

https://dortania.github.io/OpenCore-Install-Guide/installer-guide/ 

OpenCore Config (Comet Lake):

https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html

BIOS Settings:

## What Works

## What doesn't works

## Summary

## Updates

## Credits

Bootloader: 

[OpenCore](https://github.com/acidanthera/OpenCorePkg)

Guidance: 

[dhckdgjs Opencore Hackintosh settings for Gigabyte Z590 Vision-G](https://github.com/dhckdgjs/GIGABYTE-Z590-VISION-G-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580/blob/main/README.md)

[Ohchang's build: Gigabyte Z590 Vision G + i7-10700K + AMD RX580](https://www.tonymacx86.com/threads/ohchangs-build-gigabyte-z590-vision-g-i7-10700k-amd-rx580.310986/) 