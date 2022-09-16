# GIGABYTE-Z590-AORUS-PRO-AX-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580

Opencore Hackintosh settings for Gigabyte Z590 AORUS PRO AX (rev. 1.0) running macOS Big Sur 11.7 (16/09/22) and is based on  [Arrnav, Gigabyte Z590 Aorus Pro AX - 11900k - 6800XT](https://github.com/Arrnav/Gigabyte-Z590-Aorus-Pro-AX-11900k-6800XT-Opencore) and other Z590 builds. The main difference is the choice of lower spec CPU.

## Components

- GIGABYTE Z590 AORUS PRO AX (rev, 1.0, BIOS F8 with ALC4080 and i225-V) [(product page)](https://www.gigabyte.com/uk/Motherboard/Z590-AORUS-PRO-AX-rev-10#kf)
- Intel® Core™ i5-10600K 4.10GHz (Comet Lake, FCLGA1200 [(product page)](https://www.intel.com/content/www/us/en/products/sku/199311/intel-core-i510600k-processor-12m-cache-up-to-4-80-ghz/specifications.html)
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

The downloads page for the motherboard advises using BIOS F8. This is a major vulnerabilities update, customers are strongly encouraged to update to this release at the earliest.

Note from [dhckdgjs](https://github.com/dhckdgjs/GIGABYTE-Z590-VISION-G-HACKINTOSH-OPENCORE-iGPU-with-dGPU-UHD630-RX580/blob/main/README.md): GIGABYTE Z590 Vision-G M/B(BIOS F2) CAN NOT BOOT with GIGABYTE RX580 MINING or GAMING. (Compatibility issue)

It is highly recommended to boot into Windows and map your USB ports before installing macOS. Using windows is the easy route  for anyone needing custom USB mapping.

## Comments

- [OpenCore](https://github.com/acidanthera/OpenCorePkg) 0.8.4

## BIOS
 
1. Switch to BIOS (DEL)
2. Check BIOS Ver (F8 or above)
3. Load the Optimised Defaults (F7)
4. Switch to Advanced Mode (F2)

WIP:

### Favorites (F11)

* Extreme Memory Profile(X,M.P) (Disabled)
* CMS Support (Disabled)
* Secure Boot Mode (Standard)
* VT-d (Disabled, not required for this build)
* SATA Controller(s) (Enabled)

### Tweaker

* CPU Upgrade (Gaming Mode)
* Extreme Memory Profile(X.M.P.) (Disabled)

### Settings

**Platform Power**

* ErP (Disabled)
* Soft-Off by PWR-BTTN (Instant-Off)
* Resume by Alarm (Disabled)
* Power Loading (Auto)
* RC6(Render Standby) (Enabled)
* AC Back (Always Off)

**IO Ports**

* Internal Graphics (Enabled)
* DVMT Pre-Allocated (64M)
* DVMT Total Gfx Mem (256M)
* Onboard LAN Controller (Disabled)
* Above 4G Decoding (Disabled)
	* Re-Size BAR Support (Disabled, set when Enabled)
		* config.plist ResizeAppleGpuBars = -1
	* IOAPCI 24-119 Entries (Disabled, set when Enabled)
* APP Centre Downloads & Install Configuration
	* APP Centre Download & Install (Disabled)
* USB Configuration
	* Legacy Support (Enable)
	* XHCI Hand-off (Enable)
	* Mass Storage Support (Enable)
	* Port 60/64 Emulation (Enabled)
* SATA And RST Configuration
	* SATA Controller(s) (Enabled)
	* SATA Mode Selection (AHCI)
	* Aggressive LPM Support (Disabled)

**Miscellaneous**

* Intel Platform Trust Technology (PPT) (Disabled)
* VT-d (Disabled)

### System Info

No change

### Boot

* Boot NumLock State (On)
* CFG Lock (Disabled)
	* CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)
* Security Option (System)
* Windows 10 Features (Other OS)
* CMS Support (Disabled)
	* Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)
* Secure Boot
	* Preferred Operating Mode (Auto)

## Procedure

**OpenCore Install Guide**

Always refer to the OpenCore install guide for up to date instructions.

https://dortania.github.io/OpenCore-Install-Guide/

**OpenCore Config (Comet Lake)**

https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html

**Choosing the right SMBIOS**

With this combination of i5 CPU and RX580 GPU the SMBIOS choice is not simple. iMac20,1 supports Comet Lake CPU + Radeon Pro 5300, MacPro7,1 supports Cascade Lake-W CPU + Radeon Pro 580X. The advice is to start with a SMBIOS which support your CPU.

https://caizhiyuan.gitee.io/opencore-install-guide/extras/smbios-support.html

WIP:

1. ~~iMac20,1~~
2. iMac18,1
3. ~~iMac17,1~~
4. ~~MacPro7,1~~
5. ~~MacPro6,1 (working with Intel Core i5-2500 3.30GHz (Sandy Bridge) + RX 580 build)~~

## What Works

* macOS 11.7
* Wireless LAN

## What doesn't works

* Wired Lan (Ethernet)
* Bluetooth
* Sound

## Summary

## Updates

The original install was macOS 11.6.8 which was updated to 11.7 using the Apple System Preferences updater.

## Credits

Bootloader: [OpenCore](https://github.com/acidanthera/OpenCorePkg)

Guidance: [Arrnav, Gigabyte Z590 Aorus Pro AX - 11900k - 6800XT](https://github.com/Arrnav/Gigabyte-Z590-Aorus-Pro-AX-11900k-6800XT-Opencore)