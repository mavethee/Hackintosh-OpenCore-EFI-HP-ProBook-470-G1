<img src="https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Logos/OpenCore_with_text_Small.png" width="200" height="48"/>

## Hackintosh-OpenCore-HP-ProBook-470-G1
EFI premade of OpenCore bootloader for HP ProBook 470 G1 is here and runs Ventura!

## Current version - OpenCore 0.8.4 DEBUG
Repository contains full ,,Plug-and-Play" EFI of OpenCore bootloader and
all needed files to install and run macOS on HP ProBook 470 G1!

https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.4

## Important note:
EFI premade is done for people with Intel and Broadcom WiFi Bluetooth cards!

Keep in mind! For for me it's a bit weird I need to mention that. EFI is not everything, to prepare your USB with macOS installer you need to follow Dortania's Guide:
https://dortania.github.io/OpenCore-Install-Guide/installer-guide/#making-the-installer
(3 ways listed using either Windows, Linux or macOS)

If you are not using NVMe SSDs, you don't need NVMeFix kext, delete it from Kexts!
If you want to switch to RELEASE version, you can use Dortania's Guide here:

https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/debug.html

## Ventura NOTE:

Source: https://github.com/dortania/OpenCore-Legacy-Patcher/issues/998

To run Ventura, grab either `Broadcom/Ventura/EFI` or `Intel/Ventura/EFI` depending on your hardware.

Current issues with Haswell iGPUs running Ventura:

https://github.com/dortania/OpenCore-Legacy-Patcher/issues/998#issuecomment-1222926337

Get OCLP from here: https://github.com/dortania/OpenCore-Legacy-Patcher/actions?query=branch%3Aventura-alpha 

(post-install, branch in development, make sure to download artifacts for latest commit!)

OCLP preparation (already applied, listing to actually teach you something):

1. SET SIP to 0xA03:

`NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> csr-active-config` to `030A0000`

2. Disable Apple Secure Boot:

`Misc -> Security -> SecureBootModel` to `Disable` 

`Misc -> Security -> DmgLoading` to `Any`

3. Disable AMFI (+Fix for Electron apps on 12.3+):
Add `amfi_get_out_of_my_way=1 ipc_control_port_options=0` to `NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> boot-args`

4. Reset NVRAM using `ResetNvramEntry.efi` in `EFI\OC\DRIVERS`

5. (Optional) For auto root patching your unsupported dGPU generate `AutoPkgInstaller.kext` and add it to your `EFI\OC\KEXTS`:

- Launch OCLP,

- Generate EFI for Mac that has something simular to your dGPU,

- Do not install generated EFI anywhere, copy temp location and get the kext!

- Flash config.plist with generated kext, reboot to check if it works.

6. Follow OCLP prompts and reboot.

Done! GPU acceleration in Ventura is working!

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
Grab EFI from Intel folder in repo!
Depending on macOS version, you're planning to use:
* Airportitlwm for macOS 12 Monterey and delete rest.
* Airportitlwm_Big_Sur for macOS 11 Big Sur,
* Airportitlwm_Catalina for macOS 10.15 Catalina,
* Airportitlwm_Mojave for macOS 10.14 Mojave,
* Airportitlwm_High_Sierra for macOS 10.13 High Sierra.
After that rename chosen Airportitlwm kext to Airportitlwm.kext

And then make a snapshot of config.plist in ProperTree!

### If you use Broadcom:
Grab EFI from Broadcom folder in repo!

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
