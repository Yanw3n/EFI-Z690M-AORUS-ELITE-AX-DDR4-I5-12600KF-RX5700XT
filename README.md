# EFI for Intel Desktop 12600KF - Opencore 0.9.5 - Z690M AORUS ELITE AX DDR4 - macOS Sonoma 14.0 - AMD RX 5700XT

Note|Description
:----|:----
macOS|Sonoma 14.0
Motherboard|Gigabyte Z690M AORUS ELITE AX DDR4
GPU|AMD RX 5700XT
Processor|Intel® Core™ i5-12600KF
NVME SSD|Fangxiang S790 2TB
RAM|2x VENGEANCE 16Gb 3600Mhz DDR4
Wifi/Bluetooth | AX210 - Bluetooth 5.2 
Ethernet | Intel® I225-V 2.5GbE LAN
SMBIOS | iMacPro1,1

- Opencore version: 0.9.5

# Basic Steps

1. Generate and complete your SMBIOS infos - **ALWAYS**;
2. Adjust your BIOS;
3. Install macOS and enjoy :)
4. Rempap USB ports (if needed) - **ALWAYS**;

# Compatible SMBIOS

SMBIOS|Description
:----|:----
MacPro7,1|Because GPU integrated in 12th gen without support for Apple.
iMacPro1,1|Because GPU integrated in 12th gen without support for Apple.

# BIOS Settings

### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Compatibility Support Module (CSM).
- Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
	- Your hack will not boot with `CFG-Lock` enabled.

### Enable
- VT-x
- Above 4G decoding. 
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` on `boot-args` enabled at the same time.
	- When enabling Above4G, Resizable BAR Support may become an available on some motherboards. Please ensure this is **`DISABLED`** instead of set to Enabled.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- SATA Mode: AHCI
