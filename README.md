<img src="https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Logos/OpenCore_with_text_Small.png" width="200" height="48"/>

## Hackintosh-OpenCore-HP-ProBook-470-G1
EFI premade of OpenCore bootloader for HP ProBook 470 G1 is here!

## Current version - OpenCore 0.6.4 (7th December)
Repository contains full ,,Plug-and-Play" EFI of OpenCore bootloader and
all needed files to install and run macOS on HP ProBook 470 G1!

https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.4

## Important note:
EFI premade is done for people with Intel and Broadcom WiFi Bluetooth cards!

### If you use Intel:
Delete all Brcm kexts from EFI/OC/Kexts and make a snapshot of
config.plist in ProperTree!

### If you use Broadcom: 
Delete all Intel kexts from EFI/OC/Kexts

Depending on macOS version, you're planning to use:
* BrcmPatchRAM3 for 10.14+ (must be paired with BrcmBluetoothInjector)
* BrcmPatchRAM2 for 10.11-10.14
* BrcmPatchRAM for 10.8-10.10

And then, make a snapshot of config.plist in ProperTree!


## Credits:

### Airportitlwm (1.1.0):
https://github.com/OpenIntelWireless/itlwm
### AppleALC (1.5.5):
https://github.com/acidanthera/AppleALC
### Broadcom (Optional, for people who replaced Intel with it):
https://github.com/acidanthera/BrcmPatchRAM/

https://github.com/acidanthera/AirportBrcmFixup/
### IntelBluetoothFirmware (1.1.2):
https://github.com/OpenIntelWireless/IntelBluetoothFirmware
### Lilu (1.5.0):
https://github.com/acidanthera/Lilu/
### NVMeFix (1.0.4):
https://github.com/acidanthera/NVMeFix
### RealtekRTL8111 (2.3.0):
https://github.com/Mieze/RTL8111_driver_for_OS_X
### USBInjectAll (0.7.1):
https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads
### VirtualSMC (1.1.9):
https://github.com/acidanthera/VirtualSMC
### VoodooInput (1.0.9):
https://github.com/acidanthera/VoodooInput
### VoodooPS2 (2.1.9):
https://github.com/acidanthera/VoodooPS2
### WhateverGreen (1.4.5):
https://github.com/acidanthera/WhateverGreen
### OpenCanopy's resources:
https://github.com/acidanthera/OcBinaryData

## Thanks for using my EFI premade, I would be glad for some feedback! :)
