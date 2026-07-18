# TCL / BlackBerry
- Verdict: **🍅 Terrible!**

TCL got their start in the mobile world as a contract manufacturer for BlackBerry, and while TCL's contract with BlackBerry ended in 2020, TCL has continued BlackBerry's lineage of "secure bootloaders", AKA, doing everything they can to make you unable to unlock the bootloader. Because of TCL's history with BlackBerry, who has always been horrible with bootloader unlocks, it is unlikely TCL bootloaders will ever be unlockable.

## Authboot
TCL has its own fork of the fastboot utility called `authboot`, which **requires special authorization from their server to perform any bootloader-related operations**. Without this authorization, **it is impossible to unlock the device** or flash unsigned images, effectively eliminating any possibility of installing custom ROMs.

## Pre-2016 BlackBerry devices
The BlackBerry Priv and earlier were not manufactured by TCL, but by the original BlackBerry company (aka Research in Motion/RIM) in Canada. Unfortunately, even the oldest of BlackBerry's devices don't have a bootloader unlock exploit. Devices running the BlackBerry 10 operating system have a software exploit (discovered by Oleksandr) that allows to obtain root privileges though a [modded autoloader][bb10 modded autoloaders], which allows developing and running unsigned custom native applications using a [local copy of the discontinued BlackBerry 10 SDK][bb10 toolchain setup], expanding the attack surface to software exploits. As of 2026, the only BlackBerry devices which have a bootloader unlock exploit are the Passport and Priv, which can be unlocked by flashing the bootloader from a prototype device, however this requires [desoldering the phone's eMMC][passport priv unlock] and connecting it to a flasher.

## Key2 series
The BlackBerry KEY2 series of phones were manufactured by TCL with bootloaders "secured" by BlackBerry. As usual, authboot was used, as well as unlocking being useless even if you gained access. Unfortunately they did not patch out one of the worse Qualcomm bugs (CVE-2021-1931) which was an entrypoint towards [a fully untethered bootloader unlock tool][kibo]. This comes with its quirks, such as needing a modified boot image to boot the stock OS due to the restrictions BlackBerry put in place when the device is in FACTORY_MODE state.

> TCL acts premium but is nothing more than a Chinese basement. Their so‑called "security" only restricts users, while their phones are no better or safer than the rest.

***
Authored by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>
Info about authboot and engineering models by [DiabloSat](https://github.com/progzone122)<br/>

[passport priv unlock]:https://balika011.hu/blackberry/guides/passport/conversion.php
[kibo]:https://github.com/BotchedRPR/kibo
[bb10 modded autoloaders]:https://bb10.root.sx/blog
[bb10 toolchain setup]:https://forum.waitberry.com/index.php/topic,12.0.html
