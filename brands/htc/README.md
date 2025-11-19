# HTC

- Verdict: **⛔ Avoid!**
- Verdict: **🍅 Terrible!** (Unisoc/Spreadtrum)

In the past, HTC allowed you to unlock your bootloader on their [developer website], but in June 2018 for whatever reason, HTC announced that any new phones would not have unlockable bootloaders, however their developer website would remain up for older devices. A few months prior to this, HTC sold their entire phone division to Google, and simply became a name for whatever Chinese ODM wanted it; this was probably the reason for HTC killing their bootloader unlock. Unisoc and Spreadtrum devices will never be unlockable, this is *not* HTC's fault, Unisoc/Spradtrum does not allow unlocking.
> [!NOTE]
> As of September 2024, the website is still up and working (tested with an HTC Raider), however since HTC hasn't supported it in over 6 years, it may go down at any time, and even for these legacy devices, BS applies. 

## S-ON/S-OFF

HTC had a system known as "S-ON/S-OFF", with S-ON enabled, [the only partitions that can be flashed are system and recovery][s-system], all other partitions are read only. 

While HTC claims you can write boot with S-ON, it's complicated. For whatever reason, HTC made it so you can't flash boot.img from recovery, if you want to flash boot.img, you have to flash it in fastboot, meaning if you want to flash a ROM, you have to install it in recovery, then reboot to fastboot and flash boot.img, then you can boot. 

There have been systems to work around this, such as TWRP's [HTC Dumlock]. There are ways to achieve S-OFF, but it's different for each device. Search for your specific device on [XDA](https://xdaforums.com). Do note that due to the age of most of these tools, they may require legacy operating systems such as **Ubuntu 14.04 or Windows 7**.

***
Authored by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>

[developer website]:https://www.htcdev.com/bootloader
[s-system]:https://www.htcdev.com/bootloader/about_unlock_process
[HTC Dumlock]:https://xdaforums.com/t/htc-dumlock-flash-boot-from-recovery-without-fastboot-updated-2012-02-28-v2.1509743/
