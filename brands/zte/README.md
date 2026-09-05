# ZTE/nubia/Redmagic

> 🧹 This page is missing a lot of info!

- Verdict: **🍅 Just terrible!**
- Verdict: **⛔ Avoid at all costs!** (Unisoc)

## Newer devices (Snapdragon 8850/8750) 
Newer Snapdragon devices are unlockable with an exploit, including Redmagic 11 and 10, Nubia Z80 and Z70 series, and perhaps a few more (exact list unclear). Some devices require a certain security patch, while others don't. https://xdaforums.com/t/red-magic-11-pro-guide-bootloader-unlock-free-also-support-rm10-pad3pro-z70u-z80u-unlock-zte-family-toolbox.4780930/. However, the developer has recently come under scrutiny, so it's unlikely that future devices will be supported (RM12, Z90, etc.)

Unlocking often breaks the fingerprint sensor, but there is a bypass for some devices provided.

Unisoc devices will never be unlockable, this is *not* ZTE's fault, Unisoc does not allow unlocking.

## Older devices
Snapdragon-based nubia devices can be unlocked with the Fastboot command `fastboot oem nubia_unlock NUBIA_MODEL` (e.g. -- if your phone's model number is NX609J, the command would be `fastboot oem nubia_unlock NUBIA_NX609J`.). ZTE devices can also be unlocked with the standard `fastboot flashing unlock` command.

As for non-nubia ZTE devices:

Old devices (pre Android 8):<br/>
[xdaforums.com][pre-android-8]

Devices Until Android 11 with engineering firmware:<br/>
[xdaforums.com][until-android-11-few-models]

There is also a chance that your device is vulnerable to one of the MTK or Unisoc [exploits](../../README.md#universal-soc-based-methods).

Side note, on the A11 link there is a collection of apps to grant a system shell, but they would probably only work on old models.

***
Newer phones added by xMicro (9/5).
Additional info provided by [Skorpion96](https://github.com/Skorpion96).
Authored by [zenfyr](https://zenfyr.dev).

[pre-android-8]:https://xdaforums.com/t/bootloader-unlocking-on-older-qualcomm-zte-devices-devinfo-partition-modification.4100897/
[until-android-11-few-models]:https://xdaforums.com/t/zte-blade-a5-2019-2020-etc-root-guide-locked-bootloader-valid-for-all-unisoc-zte-models-with-an-engineering-firmware.4612391/
[unisoc-cve]:https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader/releases/tag/1.72
