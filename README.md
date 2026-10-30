![Banner. A lock and a key on fire on the left and the text 'Bootloader Unlock: Wall of Shame' on the right.](./misc/banner/banner.jpg)

Keeping track of companies that "care about your data 🥺"

[Switch to Russian translation](ru/README.md)

![Terrible](https://raw.githubusercontent.com/zenfyrdev/mini-badges/v1/personal/terrible.svg)
[![License CC BY-NC-SA](https://raw.githubusercontent.com/zenfyrdev/mini-badges/v1/licenses/cc/cc-by-nc-sa-4.0.svg)](https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame/blob/main/LICENSE)

<details><summary>mirrors</summary>
<p>

- GitHub: https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame
- Codeberg: https://codeberg.org/zenfyr/bootloader-unlock-wall-of-shame
- tangled: https://tangled.sh/did:plc:rjhjcb3rgdsmdr6ykywuh63z/bootloader-unlock-wall-of-shame

</p>
</details> 
Do note that issues, pull requests, and discussions on Codeberg and tangled are not monitored. Please use GitHub for these.

## What?

All Android devices ship with a locked bootloader (ABL). This means that the device will verify every loaded image against known trusted keys right from the moment it turns on.

Unlocking the bootloader means allowing the device to load images either signed with untrusted keys or not signed at all, such as custom OSes, kernels, recoveries, etc.

Most of this is powered by [Android Verified Boot](https://source.android.com/docs/security/features/verifiedboot).
Which by itself is a tool similar to [UEFI Secure Boot](https://uefi.org/specs/UEFI/2.9_A/32_Secure_Boot_and_Driver_Signing.html#secure-boot-and-driver-signing). AVB prevents the system from booting in case of corruption/compromise attempts, which is *good*, as long as the device owner can 1. Disable verification and 2. Enroll custom keys.

## Why?

Unfortunately, a lot of devices do not allow unlocking the bootloader at all, let alone enrolling a [custom root of trust](#custom-avb-keys). This is one of the many ways we see companies dismantle user choice and open platforms, with Google itself targeting things like installing "unauthorized" software with their [Android developer verification program](https://developer.android.com/developer-verification).

This list contains info on how different companies handle (or don't handle!) unlocking on devices they sell and possible ways to bypass their locks. While it mainly targets Android devices, it also has info on other device families. If you know of specific details/unlocking methods, please PR them or drop them in the [discussions](https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame/discussions).

# The list:

> [!CAUTION]
> Reminder that no matter how nice a company is, <br/>
> you should not trust them unless their unlock process is 100% offline!

## ⛔ Avoid at all costs!

The following manufacturers have made it completely impossible to unlock their devices without a workaround.

### [Alcatel](./brands/alcatel/README.md)

### [Amazon](./brands/amazon/README.md)

### [Apple](./brands/apple/README.md)

### [Asus](./brands/asus/README.md)

### [Cat](./brands/cat/README.md)

### [Coolpad](./brands/coolpad/README.md)

### [Doogee](./brands/doogee/README.md)

### [Energizer](./brands/energizer/README.md)

### [Huawei](./brands/huawei/README.md)

### [Meizu](./brands/meizu/README.md)

### [Panasonic](./brands/panasonic/README.md)

### [Samsung](./brands/samsung/README.md)

### [Sharp](./brands/sharp/README.md)

### [TCL/BlackBerry](./brands/tcl/README.md)

### [Vivo/IQOO](./brands/vivo/README.md)

### [Vsmart](./brands/Vsmart/README.md)

### [Windows phones](./brands/winphones/README.md)

### Carrier-Locked Devices

> [!NOTE]
> Phone brands handle carrier locks differently, so check your device manual or contact support.

Carrier-locked devices are the ones you get after making a commitment with a carrier of your choice. This is quite common in North America and (supposedly) allows you to save some money on your device.

As a rule, almost all carrier-locked devices do not allow the bootloader to be unlocked. This usually makes sense, as it would allow you to completely bypass the contract. The problem is that many devices still do not allow you to unlock the bootloader even after the carrier lock has been lifted. For more details, see the [carriers page](./carriers/README.md).

## 🍅 Just terrible!

The following manufacturers allow unlocking under certain conditions, such as region, model, SOC, etc., or require a sacrifice to unlock.

### [Hisense](./brands/hisense/README.md)

### [HMD/Nokia](./brands/nokia/README.md)

### [Honor](./brands/honor/README.md)

### [HTC](./brands/htc/README.md)

### [LG](./brands/lg/README.md)

### [Motorola/Lenovo/NEC](./brands/motorola/README.md)

### [OPPO/Realme](./brands/oppo/README.md)

### [Oukitel](./brands/oukitel/README.md)

### [Xiaomi/Redmi/POCO](./brands/xiaomi/README.md)

### [ZTE/nubia/Redmagic](./brands/zte/README.md)

## ⚠️ Proceed with caution!

The following manufacturers require an internet connection and/or a waiting period before unlocking.

### [Fairphone](./brands/fairphone/README.md)

### [Google/Nexus](./brands/google/README.md)

### [Infinix](./brands/infinix/README.md)

### [itel](./brands/itel/README.md)

### [OnePlus](./brands/oneplus/README.md)

### [Sony](./brands/sony/README.md)

### [Tecno](./brands/tecno/README.md)

## ℹ️ "Safe for now" :trollface: 

### [Blackview](./brands/blackview/README.md)

### [Cubot](./brands/cubot/README.md)

### [Micromax](./brands/micromax/README.md)

### [Microsoft](./brands/microsoft/README.md)

### [Nothing](./brands/nothing/README.md)

### [Shift](./brands/shift/README.md)

### [Teclast](./brands/teclast/README.md)

### [Teracube](./brands/teracube/README.md)

### [TP-Link/Neffos](./brands/tplink/README.md)

### [Ulefone](./brands/ulefone/README.md)

### [Umidigi](./brands/umidigi/README.md)

### [Volla](./brands/volla/README.md)

# Misc info

## Custom AVB Keys

Custom Android Verified Boot keys or [User-settable root of trust](https://source.android.com/docs/security/features/verifiedboot/device-state#user-settable-root-of-trust) is an optional AVB feature that allows you to run a custom OS with a locked bootloader.

It's rare to see a device that supports custom AVB keys, but some devices can be found [here](https://github.com/chenxiaolong/avbroot/issues/299).

## Universal SOC-based methods

Please check OEM-specific pages first, as there are often exceptions.

### Kirin
Kirin 620, 650, 655, 658, 659, 925, 935, 950, 960:<br/>
It's possible to unlock using test points and [PotatoNV](https://github.com/mashed-potatoes/PotatoNV) (Read the README)

### MediaTek
If you own a MediaTek device exploitable by [mtkclient](https://github.com/bkerler/mtkclient) ([fork old version](https://github.com/R0rt1z2/mtkclient)) or [Penumbra](https://github.com/shomykohai/penumbra), you can unlock the bootloader using it.<br/>

Bootloader (LK) patches can be applied via [lkpatcher](https://github.com/R0rt1z2/lkpatcher) ([web version](https://lkpatcher.r0rt1z2.com/)) or, for ARMv7 boards, via [kaeru](https://github.com/R0rt1z2/kaeru/wiki). Booting with patched LKs requires an already unlocked bootloader or may not be supported at all.

### Qualcomm 

#### Snapdragon 8 Elite Gen 5/Snapdragon 8 Elite

**Patched in February/March 2026**

On Snapdragon 8E5/8E, Qualcomm introduced a [vulnerability (CN)](https://www.cnblogs.com/sakrain/p/-/unlock-your-qualcomm) [(POC)](https://github.com/kasnria001/qualcomm_gbl_exploit_poc) where the boot process would not perform signature verification for the Generic Bootloader, so with write access to the `efisp` partition it was possible to run arbitrary code.

While the vulnerability itself is universal for the platform, it requires device/OEM-specific tricks to get root and write the GBL. Some exist for [Xiaomi devices](./brands/xiaomi/README.md#snapdragon-8-elite8gen38gen28gen1).

#### Other

The general exploit:<br/>
[alephsecurity.com](https://alephsecurity.com/2018/01/22/qualcomm-edl-2/) the bootloader unlock section.

### Unisoc
If you own a phone with the Unisoc UMS9620 or older, you can use [this](https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader) (UMS9621 needs [this](https://github.com/TomKing062/exec_addr_v2) as exec address) to achieve temporary secure boot bypass and persistently unlock the bootloader. This is valid for all devices except some devices with [modified uboot](https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader/wiki/patch_do_cboot%E2%80%90SPL#part-2-modify-fdl2ubootlk) which need [this](https://github.com/TomKing062/unisoc_chipram_signcheck_exploit) or [this](https://github.com/YC-nw/bsp_sign_fxxker) or [this](https://github.com/kasnria001/unisoc_secure_boot_bypass). Note that the method used in all three links is the same, but implemented by different people with possible differences. Also, using this, aside from unlocking the bootloader, it is possible to completely disable dm-verity by patching the trustos partition, which allows booting of unsigned partitions.

If you own a phone with the Unisoc UMS312, UMS512, or UD710, you can use [this](https://github.com/TomKing062/CVE-2022-38691_38692) exploit to achieve persistent secure boot bypass, which means all firmware, including splloader and uboot, can be modified and re-signed.

Otherwise, you can also look into this: [Spectrum_UnlockBL_Tool](https://github.com/zhuofan-16/Spectrum_UnlockBL_Tool) <br/>
This: [xdaforums.com](https://xdaforums.com/t/alldocube-t803-smile_1-bootloader-unlock-w-unisoc-t310.4393389/) <br/>
Or this: [subut](https://unisoc-android.github.io/subut/)

***
