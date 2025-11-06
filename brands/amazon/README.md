# Amazon

- Verdict: **🍅 Terrible!**

Amazon is a strange company in the Android world. They cling to old Android versions (their latest devices still ship with the EOL Android 11), they don’t include Google services on their devices, and they are **extremely aggressive towards bootloader unlocks.**

They don’t follow the standard Android bootloader unlocking procedure. Instead, they use their own implementation, which relies on a special partition called `idme`. This partition stores device-specific information such as the S/N, MAC address, and more.

The *official* way to unlock the bootloader is to flash a signed unlock image to `idme` using the command `fastboot flash unlock unlock.bin`. Of course, **this requires Amazon to sign the unlock image.**

## MediaTek
**Older MediaTek-based devices can be unlocked using [amonet]**, a bootloader/bootROM exploit [originally developed in 2019 to unlock the Amazon Fire HD 8 (2018)].

The latest devices unlocked with amonet are the Fire TV Stick 3rd Gen and Fire TV Stick Lite 1st Gen (released around 2020).

However, **Amazon has actively patched this exploit**, so even if a port of amonet exists for your device, it may still not be unlockable.

The following list shows all available amonet ports for Amazon devices, along with whether or not they have been patched. **If your device is not included in the list, it is most likely not supported**:  

- [Amazon Fire HD 6 / HD 7 (2014)]: All versions are supported; Amazon never patched these devices.
- [Amazon Fire 7 (2015 / 2017)]: All versions are supported; Amazon never patched these devices.  
- [Amazon Fire HD 8 / HD 10 (2015)]: All versions are supported; Amazon never patched these devices.  
- [Amazon Fire TV 2nd Gen (2015)]: All versions are supported; Amazon never patched this device.  
- [Amazon Fire HD 8 (2016)]: All versions are supported; Amazon never patched this device.  
- [Amazon Fire TV Stick 2nd Gen (2016)]: There are several reports of Amazon disabling **bootROM mode** on newer hardware revisions.  
- [Amazon Fire HD 8 (2017)]: All versions are supported; Amazon never patched this device.  
- [Amazon Fire HD 10 (2017)]: All versions are supported; Amazon never patched this device.
- [Amazon Echo Dot 2nd Gen (2016)]: All versions are supported; Amazon never patched this device.
- [Amazon Echo Spot 1st Gen (2017)]: All versions are supported; Amazon never patched this device.
- [Amazon Fire TV Stick 4K 1st Gen (2018)]: Devices with serial numbers containing **VM190 or higher** are shipped with **DL-Mode** disabled in **bootROM**. However, Amazon introduced a new exploit in **FireOS 6.2.8.1**, which made it possible to unlock the device even with **DL-Mode** disabled. This exploit was later patched, but there are still ways to downgrade to a supported version.  
- [Amazon Echo Show 5 1st Gen (2019)]: All versions are supported; Amazon hasn't patched this device.
- [Amazon Echo Show 8 1st Gen (2019)]: All versions are supported; Amazon hasn't patched this device.
- [Amazon Fire HD 10 (2019)]: Only a temporary, tethered exploit is available for this device. Amazon disabled **DL-Mode** in **bootROM** on all newer hardware revisions, so only early units can use this method.  
- [Amazon Fire TV Stick 3 and Fire TV Stick Lite (2020)]: Amazon patched the exploit in **FireOS 7.2.7.3**. There is a [hardware way to downgrade the device to a supported version], but it requires soldering and is not recommended for inexperienced users.  

## Qualcomm

There are also several **older Qualcomm-based devices that can be unlocked** using the [cuber exploit] ([CVE-2014-0973]):  

- [Fire TV 1st Gen (2014)]: Amazon patched this in firmware versions newer than **51.1.0.2**.  
- [All 3rd Gen Fire HDX devices (2013 ~ 2014)]: All versions are supported; Amazon never patched these devices.  

## Amlogic

For Amlogic-based devices (e.g., Fire TV Cube), multiple exploits are available. They require **DL-Mode**, which Amazon disabled on newer hardware revisions or through OTA updates (e-fuses). This list shows the available exploits:  

- [Fire TV Cube 1st Gen (2018) / Fire TV Pendant (2017)]: These devices can be unlocked as long as they haven’t been updated past **FireOS 6.2.5.8**.  
- [Fire TV Cube 2nd Gen (2019)]: This device can be unlocked as long as it hasn’t been updated past **PS7292**.  

## Conclusion

As of this writing, **no known exploits exist for unlocking the bootloader of Amazon devices released after 2020**.  

There have been multiple reports of users [purchasing engineering samples] from third-party sellers, but the firmware on these devices is useless for production units.

---

Authored by [R0rt1z2](https://github.com/R0rt1z2), [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>

[XDA Forums]:https://xdaforums.com/  

[All 3rd Gen Fire HDX devices (2013 ~ 2014)]:https://xdaforums.com/t/dev-bootloader-unlock-procedure-and-software.3030281  
[Fire TV 1st Gen (2014)]:https://xdaforums.com/t/firetv-1-bueller-full-bootloader-unlock.3031867  
[CVE-2014-0973]:https://nvd.nist.gov/vuln/detail/CVE-2014-0973  
[Cuber exploit]:https://github.com/dpeddi/Cuber  
[amonet]:https://github.com/chaosmaster/amonet  
[originally developed in 2019 to unlock the Amazon Fire HD 8 (2018)]:https://www.aftvnews.com/latest-2018-version-of-amazons-fire-hd-8-tablet-has-been-rooted-with-unlocked-bootloader/  
[Amazon Fire HD 6 / HD 7 (2014)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-hd7-hd6-ariel.4679761/  
[Amazon Fire 7 (2015 / 2017)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-downgrade-fire-7-ford-and-austin.3899860/  
[Amazon Fire HD 8 / HD 10 (2015)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-hd-8-10-2015-thebes-and-memphis.4680312/  
[Amazon Fire HD 8 (2016)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-hd-8-2016-giza.4303443/  
[Amazon Fire HD 8 (2017)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-hd-8-2017-douglas.3962846/  
[Amazon Fire HD 10 (2017)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-hd-10-2017-suez.3913639/
[Amazon Echo Spot 1st Gen (2017)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-spot-2017-rook.4754878/
[Amazon Fire TV 2nd Gen (2015)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-firetv-2-sloane.4222331/  
[Amazon Fire TV Stick 2nd Gen (2016)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-tv-stick-2nd-gen-tank.3907002/  
[Amazon Fire TV Stick 4K 1st Gen (2018)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-tv-stick-4k-mantis.3978459/  
[Amazon Fire HD 10 (2019)]:https://xdaforums.com/t/new-fire-hd10-2019-bootless-root-method-bootloader-unlock-brainstorming.3979343/page-40#post-86371571  
[Amazon Fire TV Stick 3 and Fire TV Stick Lite (2020)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-tv-stick-3-and-fire-tv-stick-lite-sheldon-p.4410297/  
[hardware way to downgrade the device to a supported version]:https://xdaforums.com/t/unlock-root-twrp-unbrick-fire-tv-stick-3-and-fire-tv-stick-lite-sheldon-p.4410297/page-47#post-89960237  
[Fire TV Cube 1st Gen (2018) / Fire TV Pendant (2017)]:https://xdaforums.com/t/root-rooting-the-firetv-cube-and-pendant-with-firefu.3861272/  
[Fire TV Cube 2nd Gen (2019)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-firetv-2nd-gen-cube-raven-ps7242.4445971/  
[purchasing engineering samples]:https://xdaforums.com/t/fire-hd-8-9th-generation-onyx-engineering-sample-with-root-access-full-fastboot.4121709/  
[Amazon Echo Dot 2nd Gen (2016)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-dot-2nd-gen-2016-biscuit.4761416
[Amazon Echo Show 5 1st Gen (2019)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-show-5-1st-gen-2019-checkers.4762900/
[Amazon Echo Show 8 1st Gen (2019)]:https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-show-8-1st-gen-2019-crown.4766687/
