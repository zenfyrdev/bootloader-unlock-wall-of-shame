# Google/Nexus

- Verdict: **⚠️ Proceed with caution!**
* [**🔓️ Unlock Guide**](../../misc/generic-unlock.md)

Allows unlocking on almost any non-carrier locked device, but is also a pioneer in making rooting and custom ROMs painful with things like Safety Net and Play Integrity. With the latest feat being RCS messaging which requires DEVICE integrity to work. (To prevent "spam", of course)

Google is also one of the few OEMs to support [custom AVB keys](../../README.md#custom-avb-keys).

Despite all of this, Google has started [disabling AI features][disabled ai] upon unlocking the bootloader on the Pixel 9 series, even if you aren't rooted, and it's not related to Play Integrity, and it's likely that in later Pixel models they'll disable more features. Some of them can be re-enabled with an [Xposed module].

## OTAConfigNoZeroTouchPrebuilt
OTAConfigNoZeroTouchPrebuilt is an app on Pixels that checks for a carrier lock. When a Pixel first connects to the internet, this system app will immediately check if the device is carrier locked. If it's not or is locked to a carrier that doesn't restrict unlocking, it will retrieve a token from Google's servers which will allow bootloader unlocks. If the token cannot be received, then the bootloader **cannot** be unlocked. This means if Google's servers ever go down, you will not be able to unlock your Pixel's bootloader, as it won't have the token.

Notably, this unlock token is persistent, both across OS reinstalls and bootloader unlocks + relocks. Once the unlock token is saved via this process, the bootloader can be forever unlocked and relocked offline. OTAConfigNoZeroTouchPrebuilt does not have any mechanism for revoking a previously granted token either. This means once you've connected to the internet, and the token has been grabbed, you can safely disconnect from the internet and even reset the phone, the bootloader unlock token will remain. 

While this is mostly a negative thing, an error can lead to carrier-locked devices being able to unlock. A few years back, Google accidentally provided unlock tokens for Verizon-locked Pixel 1's for a few days, despite Verizon being a carrier that normally completely removes the ability to unlock.

***
Additional info provided by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439) and [Andrew Gunnerson](https://github.com/chenxiaolong).<br/>
Authored by [melontini](https://github.com/melontini).

[disabled ai]:https://xdaforums.com/t/pixel-screenshots-other-ai-features-dont-work-with-unlocked-bl.4688190/
[Xposed module]:https://xdaforums.com/t/app-xposed-30-01-public-compute-services-use-aicore-features-on-rooted-devices.4775989/
