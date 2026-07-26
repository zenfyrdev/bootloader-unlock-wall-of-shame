# Windows phones

- Verdict: **⛔ Avoid at all costs!**

All Windows phones are grouped into one page due to their unlocking methods being very close and the same for a lot of devices.
None of them officially allowed bootloader unlocking, however many community methods have been developed over the years.

Make sure to disable device encryption before unlocking the bootloader with any methods below!
## Most Nokia and Microsoft phones (see exclusions below)
> [!NOTE]
> Bootloader specification A includes Lumia 52x, 62x, 72x, 810, 82x, 92x, 1020, 1320.
>
> Bootloader specification B includes Lumia 43x, 53x (except 535), 540, 550, 63x, 640, 640 XL, 650, 73x, 830, 929 Icon, 930, 950, 950 XL, 1520.
> 
An open source tool named [WPInternals][wpinternals] allows bootloader unlocking by 2 methods depending on the bootloader specification of the device.
- The first method for spec. A devices requires the stock firmware for the phone, [HEX loaders][hex-loaders], an [engineering SBL3 partition][eng-sbl3] and a [donor firmware file][donor-ffu]. The unlock mostly goes smooth, just follow the instructions of the tool.
- The second method for spec. B devices requires the stock firmware for the phone, [the correct emergency files for the device][emergency-files] and depending on your model a [donor firmware file][donor-ffu]. The unlock method **requires** that the phone is plugged in to a USB 2.0 or earlier port (a USB 2.0 hub works just fine), or you **will** encounter a "Failed to write to pipe" error. Also the unlocked bootloader flashing may get stuck at any point, if that happens reboot by holding Vol- and Power, on the red screen open WPInternals and unlock the bootloader again, repeat that until it works. If you encounter a bootloop with gears, disconnect the phone, click Interrupt Boot Process in the Manual mode tab of WPInternals and connect it while it is on the boot logo, flash the stock firmware and try unlocking again.

## Lumia 535 and other OEM devices running Windows 10 Mobile 
While no full bootloader unlocking method is made, a partial unlock allowing full file system access is possible.
You need to have Interop Tools app installed with registry access, a [guide][interop-guide] is here.
Once you have registry access, in the Registry menu navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MTP and select the DataStore key. Press Read Data and change change the string to C:\EFIESP and write the data. Connect the phone to a computer, go to Windows\System32\Boot and rename the resetphone.efi executable to anything else and replace the executable with [developermenu.efi][devmenu] and disconnect the phone from the computer.
Now reboot and hold down Vol-, you should see a developer menu. Scroll down to the USB Mass Storage Mode option by using Vol- and press Power, now you have full file system access. From here you can disable the OS's driver and system file integrity checks by enabling TESTSIGNING and NOINTEGRITYCHECKS on the BCD and unlock full sideloading capabilities, but its nowhere as close to a full bootloader unlock.

## Lumia 510, 610, 610C, 710, 800, 900
Certain Lumia 710s, 800s and 900s shipped with a Qualcomm bootloader instead of the Nokia bootloader (a way for determining is in the guide for switching 710 bootloaders). If you have a Qualcomm bootloader, your bootloader is unlocked from the factory for some reason. An unlock guide for Lumia 710s with a Nokia bootloader is available [here][lumia-wp7]. Switching the bootloader on other devices is possible with special equipment and some work. [A guide for Lumia 900][lumiawp7-blswitch] with information linking to other guides is available, but it is not specific to 900s and works on others.

## HTC phones running Windows Phone 7.x
They can be bootloader unlocked using HSPL / RSPL. There are guides for [first generation][first-gen-htc] and [second generation (except Titan II)][second-gen-htc] devices. SPL versions 4.x and 5.x are impossible to unlock, a downgrading guide is available [here][htc-downgrade-spl].

## Other devices
All Windows Phone 8.x devices can be upgraded to Windows 10 Mobile unofficially, however Windows Phone 7.x devices cant. Unfortunately, there are no workarounds for other WP7.x devices.

[wpinternals]:https://github.com/ReneLergner/WPinternals
[eng-sbl3]:https://archive.org/download/sbl-3-no-buggy-62x/SBL3_NoBuggy62x.zip
[hex-loaders]:https://4pda.to/forum/dl/post/20979092/Hex_loader.zip
[donor-ffu]:https://download.lumiadb.com/RM-1085/RM1085_1078.0053.10586.13169.12742.034EE8_retail_prod_signed.ffu
[emergency-files]:http://protobetatest.com/download/lumia-emergency-files/
[interop-guide]:https://xdaforums.com/t/interop-tools-a-versatile-registry-app-for-all-devices-now-on-github.3445271/
[devmenu]:https://archive.org/download/w10m-9821-patchedfiles/developermenu.efi
[first-gen-htc]:https://xdaforums.com/t/dft-updated-3-hspl-rspl-for-htc-wp7-first-generation.1195647/
[second-gen-htc]:https://xdaforums.com/t/dft-hspl-for-htc-wp7-second-generation.1684912/
[htc-downgrade-spl]:https://xdaforums.com/t/noob-friendly-goldcard-spl-downgrade-method-no-android-phone-and-or-custom-wires.1597837/
[lumia-wp7]:https://xdaforums.com/t/tutorial-full-unlock-lumia-710-in-windows-using-nss-pro-detailed-updated.1721355/
[lumiawp7-blswitch]:https://xdaforums.com/t/how-to-bootloader-unlock-your-lumia-900-and-flash-a-custom-rom.2204994/post-39517020
