# OnePlus

* Verdict **⚠️ Proceed with caution!**
* Global phones or Chinese phones released with ColorOS 15 or older: [**🔓️ Unlock Guide**](../../misc/generic-unlock.md)

## Global phones and older Chinese models
All OnePlus phones on the global market, and any Chinese models that were initially released with ColorOS 15 or older, can be easily unlocked using the [standard procedure](../../misc/generic-unlock.md). This includes devices that have since updated to ColorOS 16.0 or newer.

## Newer Chinese phones initially released with ColorOS 16.0 and above
According to the [OnePlus forum](https://bbs.oneplus.com/thread/1926504022886318086), for phones and tablets sold in mainland China, unlocking the bootloader is **only possible via an official application to join the “Deep Testing” program**. After submitting a unlock request they normally take 2 days to be approved.
**Main requirements:**  
- Account must be in good standing (no violations or restrictions)  
- No application submitted in the past 30 days  
- Device is not a corporate or carrier-customized model  

> **Note:** These restrictions currently apply only to devices sold in mainland China. However, due to the unified OPPO–OnePlus codebase, similar restrictions may be introduced for global models in the future.

Note that starting September, 2026, OnePlus will make "Deep Testing" program much harder (even on coloros16, not just coloros17+) ([link to OnePlus forum](https://bbs.oneplus.com/thread/2175833961601695750)). Note that this only applies to Chinese versions of OnePlus smartphones. It now requires:
- your real name
- face verification
- 7-day account login requirement
- 7-day approval process
- 14-day unlock window
- Limited monthly unlock slots

Even though OxygenOS 17 is officially cancelled (every version of OnePlus 16 will be initially released with ColorOS 17), "Deep Testing" program will be needed only on Chinese versions.

Note that if you updated your OnePlus 11-15 to ColorOS 17 (when it will be released) and downgraded it to OxygenOS 16 through official Rollback package (note that it is not released yet), you will not be able to flash any custom ROM based on android 16 other than that Rollback package, because this package has patched ARB index.

### How to check your ARB index

Go to fastboot mode and enter this command:

```console
$ fastboot getvar anti
```

If it says `0`, you can do anything with your phone. If it says `1`, you cannot downgrade your phone to android 15. If it says `2`, you cannot downgrade your phone to android 16.

> **Note:** This information may not be correct because ColorOS 17 and OnePlus 16 are not released yet

## T-Mobile
For OnePlus devices purchased from T-Mobile or an MVNO such as Metro, even if the device was later unlocked from T-Mobile, they require an [unlock token], and to get your unlock token, you need to provide original proof of purchase from T-Mobile. If you purchased the device from eBay, you will not be able to unlock your bootloader. This does not apply to the OnePlus 6 or earlier. This doesn't appear to apply to other third party sellers (such as OLX).

***
Authored by [madeline-yana](https://github.com/madeline-yana) and [jotkauser](https://github.com/jotkauser).

Information about the Deep Testing program by [DiabloSat](https://github.com/progzone122).

[unlock token]:https://www.oneplus.com/us/unlock_token
