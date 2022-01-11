<img src="https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Logos/OpenCore_with_text_Small.png" width="200" height="48"/>

## Hackintosh-OpenCore-HP-ProBook-470-G1
EFI premade of OpenCore bootloader for HP ProBook 470 G1 is here!

## Current version - OpenCore 0.7.7 (11th January 2022!)
Repository contains full ,,Plug-and-Play" EFI of OpenCore bootloader and
all needed files to install and run macOS on HP ProBook 470 G1!

https://github.com/acidanthera/OpenCorePkg/releases/tag/0.7.7

## Important note:
EFI premade is done for people with Intel and Broadcom WiFi Bluetooth cards!

Keep in mind! For for me it's a bit weird I need to mention that. EFI is not everything, to prepare your USB with macOS installer you need to follow Dortania's Guide:
https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer
(3 ways listed using either Windows, Linux or macOS)

If you are not using NVMe SSDs, you don't need NVMeFix kext, delete it from Kexts!
If you want to switch to RELEASE version, you can use Dortania's Guide here:

https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/debug.html

### SMBIOS:
Present in repo SMBIOS is not purchased Apple's device but for own sake, I don't advice you to use it.
...for own sake ;)

To generate SMBIOS you can use:
* GenSMBIOS:
https://github.com/corpnewt/GenSMBIOS
* OpenCore Auxiliary Tools:
https://github.com/ic005k/QtOpenCoreConfig

Tool doesn't matter really, you just need not valid or unused SMBIOS to copy-paste needed info.
...if you wish to use iServices of course :)

### If you use Intel:
Delete all Brcm kexts from EFI/OC/Kexts, 
Depending on macOS version, you're planning to use:
* Airportitlwm for macOS 12 Monterey and delete rest.
* Airportitlwm_Big_Sur for macOS 11 Big Sur,
* Airportitlwm_Catalina for macOS 10.15 Catalina,
* Airportitlwm_Mojave for macOS 10.14 Mojave,
* Airportitlwm_High_Sierra for macOS 10.13 High Sierra.
After that rename chosen Airportitlwm kext to Airportitlwm.kext

And then make a snapshot of config.plist in ProperTree!

### If you use Broadcom: 
Delete all Intel kexts from EFI/OC/Kexts

Depending on macOS version, you're planning to use:
* BrcmPatchRAM3 for 10.14+ (must be paired with BrcmBluetoothInjector)
* BrcmPatchRAM2 for 10.11-10.14
* BrcmPatchRAM for 10.8-10.10

And then, make a snapshot of config.plist in ProperTree!


## Credits:

### Airportitlwm:
https://github.com/OpenIntelWireless/itlwm
### AppleALC:
https://github.com/acidanthera/AppleALC
### Broadcom (Optional, for people who replaced Intel with it):
https://github.com/acidanthera/BrcmPatchRAM/

https://github.com/acidanthera/AirportBrcmFixup/
### IntelBluetoothFirmware:
https://github.com/OpenIntelWireless/IntelBluetoothFirmware
### Lilu:
https://github.com/acidanthera/Lilu/
### NVMeFix:
https://github.com/acidanthera/NVMeFix
### RealtekRTL8111:
https://github.com/Mieze/RTL8111_driver_for_OS_X
### USBInjectAll:
https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads
### VirtualSMC:
https://github.com/acidanthera/VirtualSMC
### VoodooInput:
https://github.com/acidanthera/VoodooInput
### VoodooPS2:
https://github.com/acidanthera/VoodooPS2
### WhateverGreen:
https://github.com/acidanthera/WhateverGreen
### OpenCanopy's resources:
https://github.com/acidanthera/OcBinaryData

## Thanks for using my EFI premade, I would be glad for some feedback! :)
