# Sony

- Verdict: **⚠️ Proceed with caution!** (international Xperia)

- Verdict: **🍅 Terrible!** (Japan Xperias, non-Xperia devices)

Sony has an open policy for software developers:
- They are releasing AOSP sources under [Sony Open Devices Program].
- Jolla provides first-class support for installing [Sailfish OS] on select Xperias.

Since Sony likes to ruin a perfect thing:
- Sony requires you to request an unlock code from their [Unlock Service]. They can pull the plug anytime. You have to send your IMEI and agree to possible warranty voiding (many have had their phones repaired/replaced under warranty even after unlocking, just simply flash stock and lock before doing warranty).

Some carrier locked and US devices can never be unlocked. On Sony devices ([but not all?][service-menu-gone]) you can check if the bootloader is unlockable using the service menu.

Additonally, only Xperia (Sony's main consumer phone/tablet line) is unlockable. Their other Android devices (such as their [Bravia TVs][Bravia unlock]) are not unlockable.

1. Dial `*#*#7378423#*#*` in the dialer.
2. Tap "Service Info", then "Configuration", then "Rooting Status".
3. Under Rooting Status look for "Bootloader unlock allowed"
4. If "Yes", then the device is unlockable.

For devices made [before 2019][TA patch 2019], Sony devices have a partition called `TA`, which contains files needed for things such as enhanced camera image processing, DRM keys, and display enhancements. Upon unlocking the bootloader, this partition is wiped and these features are lost, even on re-locking. If running Android Marshmallow or earlier, you can [back up][TA backup] the partition. 

Sony supports [Custom AVB](../../README.md#custom-avb-keys) Since 2020.

You also can't unlock Japan carrier variants, for some reason - Japanese factory unlocked is unaffected.

All Sony devices using the Snapdragon 835 and Snapdragon 845 can be unlocked via the [xperable exploit][xperable].

***
Info about Japan devices provided by [madeline-yana](https://github.com/madeline-yana) and edited by [eepymeowers](https://github.com/eepymeowers)
Additional info provided by [K4sum1](https://github.com/K4sum1).<br/>
Authored by [konradmb](https://github.com/konradmb).

[Sony Open Devices Program]:https://developer.sony.com/open-source/aosp-on-xperia-open-devices
[Sailfish OS]:https://shop.jolla.com/
[Unlock Service]:https://developer.sony.com/open-source/aosp-on-xperia-open-devices/get-started/unlock-bootloader
[service-menu-gone]:https://www.reddit.com/r/SonyXperia/comments/qir0ze/what_happened_to_the_service_menu/
[TA patch 2019]:https://www.reddit.com/r/SonyXperia/comments/1199y1j/what_are_the_consequences_of_getting_rid_off_the/
[TA backup]:https://together.jolla.com/question/168711/xperia-x-backup-ta-partition-before-unlocking-bootloader/
[Bravia unlock]:https://pro-bravia.sony.net/data/bz40h/ProBRAVIA_SecurityWhitePaper.pdf
[xperable]:https://github.com/j4nn/xperable
