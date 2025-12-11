# OPPO/Realme

> 🧹 Deep Testing section needs apk links.
>
> 🧹 There should be a guide to running code with the debuggable apk.

- Verdict: **⛔ Avoid!**

## Realme

Realme, allows unlocking for supported models and regions. China and India models are confirmed to be supported, with some models from other regions reportedly supported as well. 

To unlock, you need to submit a request through the deep testing app that they publish on their forum. You'll have to find and follow instructions at [c.realme.com](https://c.realme.com/in/). The process is pretty much the same for most phones, but newer models may require a HeyTap account.

### Unofficial Unlock

- [💡 Universal SOC-based methods](../../README.md#universal-soc-based-methods)

#### Region Switching

In theory, if available, you could use full-OTA packages to change your phone's firmware region and use the deep testing app directly, but I can't verify that this works (please, correct me if I'm wrong). Guide: [xdaforums.com][Full-OTA region switch]

#### Server Exploit (Obsolete)

In April-May 2023 you could unlock any Realme phone using this script [rmx3474-rooting], but on May 26th Realme posted this announcement on their forum [c.realme.com][announcement]. (They've deleted the original announcement)
Since then, they have forced their servers to only return "new struct" keys, which have model data attached, making the script useless.

## OPPO
>If bootloader unlocking doesn't work on an Oppo Mediatek device using the SECCFG mod (unlocking via mtkclient), you can try unlocking fastboot by writing a >modified boot1 (preloader). Writing a preloader also uses mtckclient: [oppo-mtk-fastboot-unlock](https://github.com/Shocked-Cat/oppo-mtk-fastboot-unlock).

There's not much else to say about OPPO. They also offer in-depth testing, but only for Chinese models

## Deep Testing

Deep Testing is the application used to request the fastboot key. Internally, it writes the key to the (oplus/oppo)reserve1 partition, which is later read by fastboot. Realme and Oppo have different versions of Deep Testing, but the apps are almost identical in function.

### Realme

While Realme's posts make it seem like you need a specific version of DT for each device, this is not true. All devices with RUI 2 and below need to use v1.0.0, all devices with RUI 3 and above need to use v1.0.1 or v1.1.0.

**v1.0.1:**
- Changes the signing key.

**v1.1.0:**
- Introduces HeyTap accounts.

#### Debugging

A debuggable version of Deep Testing 1.1.0 has been accidentally released. Equipped with Android Studio, you can execute code with full system privileges (UID 1000, not root).

Brought up by [gargargar666 on XDA][deep-testing-thread]. Download [GT5-DeepTesting.apk][debuggable-deep-testing]

### Oppo

Oppo Deep Testing uses a different API endpoint to request the unlock code. Only 2 versions of Oppo Deep Testing exist: v1.0.1 and v1.1.0.

***
Authored by [melontini](https://github.com/melontini).

[rmx3474-rooting]:https://github.com/turistu/rmx3474-rooting
[announcement]:https://c.realme.com/in/post-details/1671137365285982208
[Full-OTA region switch]:https://xdaforums.com/t/change-region-via-full-ota.4535659/
[deep-testing-thread]:https://xdaforums.com/t/discussion-a-thread-to-collate-and-share-what-is-known-about-unlocking-fastboot-on-oppo-devices.4490041/post-89323153
[debuggable-deep-testing]:https://xdaforums.com/attachments/gt5-deeptesting-apk.6065115/
