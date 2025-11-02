# Samsung

- Verdict: **🍅 Terrible!**
* [**🔓️ Unlock Guide (supported devices)**](../../misc/samsung-unlock.md)

If you have a North American device and were lucky enough not to update for a while, you can check out [this paid service][Paid North American Unlock] at your own risk. Exynos devices, regardless of region, can be unlocked assuming you're on One UI 7 or earlier. 

Until recently, international Samsung devices (e.g. ones sold in Europe or Asia) were unlockable, however, starting with One UI 8, Samsung has [completly nuked][One UI 8 Unlock] bootloader-unlock option. NOTE: it is still possible in some cases to update to One UI 8, but only if you follow very specific, careful flashing rules — do not treat this as a safe or supported path (see the [Unlock Guide](../../misc/samsung-unlock.md) 

Despite the removal of bootloader unlocks in One UI 8, the Galaxy XR, Samsung's AR headset, [does have][xr bootloader unlock] an unlockable bootloader.

Snapdragon phones prior to the S7/Note7 (2016) can be unlocked regardless of region, as long as it's not locked to a carrier like AT&T or Verizon. The Canadian S7 can also be unlocked as it uses an Exynos SoC, despite Canada normally being a Snapdragon region.

**Be aware that unlocking a Samsung device will permanently trip Knox.** As a result, many Knox-based features will be broken. This includes, but not limited to: Samsung Pay, Pass, Flow, Health, Secure Folder, Secure Wi-Fi, Smart View. Furthermore, tripping Knox may serve as grounds for voiding your warranty.

There have been hardware issues caused by unlocking the bootloader, but these have been fixed for some regions. See [here][1] and [here][2]. As of late 2023, Korean Galaxy Fold3 running OneUI 5 still got camera disabled after unlocking, while EU/CN variants had fixed the issue.

As of September 2025, Galaxy Z Fold 5 also has a camera issue after unlocking the bootloader. After analyzing it, we found out it is a "Security Mechanism" to prevent the user from "taking photos" once they unlock the bootloader by providing a "black screen" in the viewfinder. (Fixable by re-locking the bootloader)

---

🔶 As of October 2025, all budget phones that have **Helio G99**, **Dimensity 6100+**, and **Dimensity 6300** have **serious connectivity and unfixable bootloop issues** after unlocking the bootloader and flashing a custom binary which "trips Knox".

**Example Devices Affected:**
- **Helio G99:** Galaxy A15 4G, A16 4G, etc.
- **Dimensity 6100+/6300:** Galaxy A06 5G, A15 5G, M15 5G, A16 5G, etc.

**If your device has Helio G99 or Dimensity 6100+/6300, you are a victim too!**

As a result, in the Helio G99 models, the **entire modem** will crash every 6 hours, causing your SIM cards to be disabled and showing a temporary NULL IMEI in the settings.

<details>
<summary>Click to expand image</summary>

![G99 Modem Issue](resources/G99_modem_issue.jpg)

</details>

Once the modem crashes after 6 hours, **there's no way to get it up and running again**. We even tried cutting off power to the modem and giving it back using a kernel-level hack, but it didn’t fix the issue either.

The only solutions are restarting the phone or using "third-party" Magisk module to restart the `ril-daemon` before the modem crash occurs every 6 hours.

**This remains unfixable even after re-locking the bootloader!**

🔶 In the Dimensity 6100+/6300 models, **you will completely lose 5G connectivity permanently**, and this is unfixable even after re-locking the bootloader. **The modem will crash when connecting to a 5G network**, leading to high battery drain and overheating. The only fix as of now is putting your device in 4G mode.

<details>
<summary><b>Expand to view proofs</b></summary>

https://github.com/user-attachments/assets/dcf5c6d6-59fb-4e8c-9a1c-d44888f0a0d4

</details>

After intense analysis by ~5 experienced members of the Helio G99 and Dimensity 6100+/6300 community, we found why this happens. It looks like Samsung implemented checks at **both the modem firmware level and software level** to check for the value of the property `ro.vendor.boot.warranty_bit`. The software check uses a function called `DoOemSetwarrantyBit` in `/vendor/lib64/libsec-ril.so`.

**Why does a RIL-related HAL need to check "is Knox tripped?"**

After patching the necessary libs in the vendor, we thought it was over until we found out 5G still wasn't working and discovered that a similar but different function is baked into the modem firmware itself by analyzing the contents of the `md1img` partition. 


<details>
<summary>Click to expand image</summary>

![Possible kill switch ?](resources/modem_strings.png)

*Possible kill switch ?*

</details>

**This firmware check differs from the libsec-ril's function and isn't patchable by a third party.**

We even tried porting an entire vendor from another Samsung 5G device. Even though the device boots and everything is fully functional, it didn’t fix the 5G issue, which means this problem is buried deep in the firmware!

> [!WARNING]
> The only fix is to be aware of this issue and not unlock the bootloader and trip Knox in the first place if you don't like these consequences. You have to sacrifice something to root these 2 device types.

---

**🔴 Regarding the unfixable bootloop issue in Dimensity 6100+/6300**, it literally feels like a hard brick. The only thing that works is the display turning on. No matter what you do, even after flashing the stock ROM and re-locking the bootloader, this issue remains unfixable.

<details>
<summary><b>Expand to view proofs</b></summary>

https://github.com/user-attachments/assets/5338f5fc-5b0b-4e03-a179-9092bd54d841

</details>

This was a serious issue in the initial firmware of the Dimensity 6100+ and 6300 devices and was **fixed by later firmware updates.**

If you want to unlock the bootloader, first update your phone to any firmware released with the 2025 January/April/July security patch.

**Symptoms:**
1. User can unlock the bootloader without any issues and the phone boots normally.
2. When they attempt to flash an unsigned binary (such as a custom kernel or Magisk-patched AP/boot image), the boot process instantly crashes after the splash screen (first Samsung Galaxy logo).
   - What it looks like: A grey fuzzy screen with vertical blue/yellow lines appears when the crash occurs.
3. This issue is unfixable even after reverting the changes, and **you cannot access Android recovery - only download mode remains accessible.**

**There is nothing to worry about regarding this issue if your phone firmware is already updated.**

**Sources:**
- As the [writer of this section](https://github.com/ravindu644) of this documentation, I personally experienced this issue and lost $200.
- [XDA Forum post regarding this exact issue](https://xdaforums.com/t/bootloop-without-access-to-recovery-need-insights-a156e-dsn.4707443/)

---

## SoC level exploits
One of the first things Samsung bootloaders do on phone bootup is check if the bootloader is unlocked, and if it is, and a bootloader unlock has not been authorized, the bootloader will automatically relock. This means SoC level exploits such as mtkclient or EDLUnlock will not work on Samsung devices, unless you reverse engineer, modify and re-flash Samsung's bootloader to stop the bootloader from re-locking. 

## KnoxPatch

Some of Knox-based features can be fixed with this LSPosed module [KnoxPatch] and its companion Magisk/KernelSU module [KnoxPatch#knoxpatch-enhancer].

## VoLTE on Custom ROMs

Samsung's IMS service is not compatible with AOSP's, so VoLTE will not work on GSI ROMs.

There is an [open source VoLTE service] developed by phh, but it's incomplete and not stable.

***
Additional info provided by [aries-ts-indo](https://github.com/aries-ts-indo), [ravindu644](https://github.com/ravindu644) and [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>
Authored by [melontini](https://github.com/melontini).

[1]:https://www.xda-developers.com/bootloader-unlocking-no-longer-kills-galaxy-z-fold-3-cameras/
[2]:https://www.xda-developers.com/samsung-galaxy-s22-bootloader-unlock-camera-working/

[open source VoLTE service]:https://github.com/phhusson/ims
[Paid North American Unlock]:https://xdaforums.com/t/android-unsamlock-bootloader-unlock-for-samsung-us-canada-devices.4215101/
[KnoxPatch]:https://github.com/BlackMesa123/KnoxPatch
[KnoxPatch#knoxpatch-enhancer]:https://github.com/BlackMesa123/KnoxPatch#knoxpatch-enhancer
[One UI 8 Unlock]:https://xdaforums.com/t/bootloader-unlocking-option-removed-from-one-ui-8-0.4751904/
[xr bootloader unlock]:https://www.ithome.com/0/892/132.htm
