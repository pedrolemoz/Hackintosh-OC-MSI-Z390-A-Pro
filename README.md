# OpenCore Hackintosh for Z390-A Pro Motherboard

> This EFI was tested in MacOS Monterey using i5-9600K processor with iGPU

<p align="center">
  <img src="https://raw.githubusercontent.com/pedrolemoz/Hackintosh-OC-MSI-Z390-A-Pro/master/Assets/macOS_Monterey_Z390-A_Pro.png"/>

This EFI is based on the core version provided from [Dortania's guide](https://dortania.github.io/) with some adjustments to work on MSI Z390-A Pro. You can't use this EFI without generating your own data with GenSMBIOS. Current supported version: 0.7.5

## Requirements to edit the EFI

- [Python3](https://www.python.org/downloads/)
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

## BIOS configuration

Press F7 to enter the advanced mode (or click in the button at top)

Restore the default configuration (Settings -> Save & Exit -> Restore Defaults)

Find and change accordingly:

|Configuration|Value|
|-|-|
|Serial(COM) Port0|Disabled|
|Parallel(LPT) Port|Disabled|
|Above 4G MMIO BIOS assignment|Enabled|
|Initiate Graphic Adapter|IGD|
|Windows 10 WHQL Support|UEFI|
|Secure Boot|Disabled|
|Boot mode select|UEFI|
|Above 4G memory/Crypto Currency mining|Enabled|
|CFG Lock|Disabled|
