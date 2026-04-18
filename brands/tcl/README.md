# TCL / BlackBerry
- Verdict: **🍅 Terrible!**

TCL got their start in the mobile world as a contract manufacturer for BlackBerry, and while TCL's contract with BlackBerry ended in 2020, TCL has continued BlackBerry's lineage of "secure bootloaders", AKA, doing everything they can to make you unable to unlock the bootloader. Because of TCL's history with BlackBerry, who has always been horrible with bootloader unlocks, it is unlikely TCL bootloaders will ever be unlockable.

## Authboot
TCL has its own fork of the fastboot utility called `authboot`, which **requires special authorization from their server to perform any bootloader-related operations**. Without this authorization, **it is impossible to unlock the device** or flash unsigned images, effectively eliminating any possibility of installing custom ROMs.

## Pre-2016 BlackBerry devices
The BlackBerry Priv and earlier were not manufactured by TCL, but by the original BlackBerry company (aka Research in Motion/RIM) in Canada. Unfortunately, even the oldest of BlackBerry's devices haven't been cracked, and with the shutdown of all services for BB10 and BlackBerry Tablet OS on January 4, 2022, it is now impossible to create apps for these platforms, restricting a potential bootloader unlock to a hardware level exploit only, as it is now basically impossible to do anything with the software. As of 2025, the only BlackBerry devices which have a bootloader unlock exploit are the Passport and Priv, which can be unlocked by flashing the bootloader from a prototype device, however this requires [desoldering the phone's eMMC][passport priv unlock] and connecting it to a flasher.

> TCL acts premium but is nothing more than a Chinese basement. Their so‑called "security" only restricts users, while their phones are no better or safer than the rest.

***
Authored by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>
Info about authboot and engineering models by [DiabloSat](https://github.com/progzone122)<br/>

[passport priv unlock]:https://balika011.hu/blackberry/guides/passport/conversion.php
