# OpenCore Hackintosh for Z390-A Pro Motherboard

> This EFI was tested in MacOS Sonoma using i7-9700K processor with iGPU

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/macOS_Sonoma_Z390-A_Pro.png"/>

This EFI is based on the core version provided from [Dortania's guide](https://dortania.github.io/) with some adjustments to work on MSI Z390-A Pro. You can't use this EFI without generating your own data with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). Seriously, it WILL NOT BOOT. Current OpenCore supported version: 1.0.2

## Hardware used to create this EFI

| Component   | Hardware                 |
| ----------- | ------------------------ |
| Motherboard | MSI Z390-A Pro           |
| CPU         | Intel Core i7-9700K      |
| dGPU        | RTX 3060 OC 12 GB (EVGA) |
| iGPU        | Intel UHD 630            |
| RAM         | 16 GB DDR4 3200 MHz      |

> Any `dGPU` will be disabled with this EFI. Check the instructions below if you have a supported one. 

## Requirements to edit the EFI

- [Python3](https://www.python.org/downloads/)
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

In GenSMBIOS, use `iMac19,1` as parameter to generate info.
In ProperTree, go to `PlatformInfo` -> `Generic` and place the corresponding data in their respective fields:

| GenSMBIOS generated info | config.plist       |
| ------------------------ | ------------------ |
| Type                     | SystemProductName  |
| Serial                   | SystemSerialNumber |
| Board Serial             | MLB                |
| SmUUID                   | SystemUUID         |

As mentioned early, any `dGPU` will be disabled. To enable a supported `dGPU`, go to `NVRAM` -> `Add` -> `7C436110-AB2A-4BBB-A880-FE41995C9F82` -> `boot-args` and remove the `-wegnoegpu` flag.

## BIOS Configuration

In order to boot this EFI, you'll need to configure the motherboard BIOS.
I've made a custom configuration file, and you can download it by [clicking here](https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/bios_config.ocb).

### How to install this configuration file

First of all, make sure to be in BIOS version `E7B98IMS.1E1`.
If you aren't in this version, please update your system.
You can find newer versions in [MSI website](https://www.msi.com/Motherboard/Z390-A-PRO/support).
Futhermore, backup your current config to avoid mistakes.

First, click in the advanced button, at the top

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/1.bmp"/>

Go to the `OC Profile` section, at the right

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/2.bmp"/>

Select the `OC Profile Load from USB` option

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/3.bmp"/>

Select the downloaded file in your USB device and press enter

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/4.bmp"/>

If everything is done successfully, you'll see this screen:

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/5.bmp"/>