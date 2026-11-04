# OPPO/Realme

> 🧹 Deep Testing section needs apk links.  
> 🧹 There should be a guide to running code with the debuggable apk.

- Verdict: **🍅 Just terrible!**


### Unofficial Unlock (Realme and Oppo)

> [!NOTE]
> If bootloader unlocking doesn't work on an Oppo Mediatek device using the SECCFG mod (unlocking via mtkclient), you can try unlocking fastboot by writing a >modified boot1 (preloader).<br/>
> Writing a preloader also uses mtkclient: [oppo-mtk-fastboot-unlock](https://github.com/Shocked-Cat/oppo-mtk-fastboot-unlock).

- [💡 Universal SOC-based methods](../../README.md#universal-soc-based-methods)

After unlocking, both OPPO and Realme MTK bootloaders can be patched to enable fastboot via [lkpatcher](https://github.com/R0rt1z2/lkpatcher) ([web version](https://lkpatcher.r0rt1z2.com/))

## Realme

Realme, allows unlocking for supported models and regions. China and India models are confirmed to be supported, with some models from other regions reportedly supported as well. 

To unlock, you need to submit a request through the deep testing app that they publish on their forum. You'll have to find and follow instructions at [c.realme.com](https://c.realme.com/in/). The process is pretty much the same for most phones, but newer models may require a HeyTap account.

### Unofficial Unlock

#### Region Switching

In theory, if available, you could use full-OTA packages to change your phone's firmware region and use the deep testing app directly, but I can't verify that this works (please, correct me if I'm wrong). Guide: [xdaforums.com][Full-OTA region switch]

#### Server Exploit (Obsolete)

In April-May 2023 you could unlock any Realme phone using this script [rmx3474-rooting], but on May 26th Realme posted this announcement on their forum [c.realme.com][announcement]. (They've deleted the original announcement)
Since then, they have forced their servers to only return "new struct" keys, which have model data attached, making the script useless.

#### Case Study: Realme 12x 5G (RMX3998) — Full Security Audit (Nov 2026)

> Complete reverse engineering of the Realme 12x 5G (MT6835 / Dimensity 6100+, Android 16, realme UI 6/7).
> Every unlock path was attempted and documented. The device is currently **impossible to root or bootloader-unlock** without realme's private signing key.
>
> **This research was conducted on a personally owned device for educational purposes only.**

| Layer | Protection | Bypass Attempted | Result |
|---|---|---|---|
| Boot ROM (MTK V6) | Carbonara + HeapBait patched in mask ROM | mtkclient | ❌ Silent to legacy handshake |
| Bootloader (LK) | Unlock flag in OPLUSreserve1, protected by runtime-derived 32-byte magic (TZ-derived) | Static forgery | ❌ Magic is runtime, not static |
| fastbootd | Refuses flash on locked devices | Direct flash | ❌ "Command not available on locked devices" |
| OTA server | Model whitelist — RMX3998 not approved | Direct API with spoofed/supported models | ❌ -1002 for ALL models (server shut down for all since May 2023) |
| Deep Testing APK | Platform signing key rotated between Android versions | APK install | ❌ "oplus named app is not match signature" |
| OTA app (update_engine) | RecoverySystem.verifyPackage requires realme signature | Local install with unsigned payload | ❌ Signature verification fails |

##### Key Technical Findings

- The `subsystem_daemon` SELinux domain (which executes `/odm/bin/init.subsys.sh`) has **blk_file read/write** access to `oplusreserve*` block devices, and `/odm` has **no dm-verity/AVB descriptor** — if a payload could write a modified script to odm, it would run as root at boot and could modify the unlock flag. The delivery mechanism (getting update_engine to accept the payload) is the unsolved problem.
- The `OplusEngineerService` binder interface has 15 methods; `fastbootUnlock` is among them but requires a valid unlock token signed by realme's private key.
- Realme's deep testing server (`lkf.realmemobile.com`) is still alive but returns `-1002` ("model not supported") for **all models**, including previously supported ones (RMX3461, RMX3474). The server was shut down for all devices in May 2023.
- The `RecoverySystem.verifyPackage` check in update_engine requires a valid PKCS#7 signature from a cert in `otacerts.zip` (realme's platform cert, valid until 2046).
- The local OTA install path (`forbid_ota_local_update=false`) is available but gated behind `LocalUpdateVerify()` which requires a realme-signed grant token: `RSA_public_decrypt(grant, embedded_pubkey, RSA_PKCS1_PADDING)` with device-ID binding and server-side timestamp validation.

##### Tools Used

- Ghidra 12.1.4 (ARM64 decompilation of update_engine, LK bootloader)
- avbtool (AVB descriptor analysis)
- Custom Python OTA query client (working — queries realme's encrypted OTA API)
- apktool + jadx (APK decompilation of Deep Testing, OTA app, Engineer Mode)

##### Credit

Full research notes available at [mrbeandev/realme-12x-security-research](https://github.com/mrbeandev/realme-12x-security-research).


## OPPO

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
Authored by [zenfyr](https://zenfyr.dev).

[rmx3474-rooting]:https://github.com/turistu/rmx3474-rooting
[announcement]:https://c.realme.com/in/post-details/1671137365285982208
[Full-OTA region switch]:https://xdaforums.com/t/change-region-via-full-ota.4535659/
[deep-testing-thread]:https://xdaforums.com/t/discussion-a-thread-to-collate-and-share-what-is-known-about-unlocking-fastboot-on-oppo-devices.4490041/post-89323153
[debuggable-deep-testing]:https://xdaforums.com/attachments/gt5-deeptesting-apk.6065115/
