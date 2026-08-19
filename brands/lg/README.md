# LG

- Verdict: **🍅 Just terrible!**
- Verdict: **⛔ Avoid at all costs!** (Unisoc)
- Verdict: **ℹ️ Safe for now** (Watches) :trollface:

In the past, LG had a developer portal which could be used to unlock phones on their website, however it only supported **some** international models of their phones, but in December 2021, LG [announced][announcement-archive] the developer portal would be shutting down due to LG ending production of all phones. Unisoc devices will never be unlockable, this is *not* LG's fault, Unisoc does not officially support unlocking.

On some models (such as the Stylo 3 Plus and G6), the bootloader can still be officially unlocked via `fastboot oem unlock` **only if** [the phone is a T-Mobile model][t-mobile-unlock]. T-Mobile versions also have most fastboot commands removed, including `fastboot flash`, `erase` and `boot` since the [LG V10 on Android 6][TMO Fastboot commands removed].

Older devices (prior to 2015) do not have partition verification (on operating system versions made prior to 2015) and assuming you have a root exploit, you can just flash modified partitions with dd -- as recommended by some official LineageOS [install guides]

Newer LG budget phones (2018+) from the K and Stylo series typically do not have Fastboot.

Most carrier branded LG devices (aside from T-Mobile versions) also usually have hidden or no Fastboot as well.

## Watches
All LG watches on Android Wear/Wear OS use the [standard unlock procedure](../../misc/generic-unlock.md) via fastboot.

## Unofficial methods
Aside from the generic unofficial methods for devices with MediaTek and Unisoc SoCs, some of their devices with Qualcomm SoCs have leaked engineering bootloaders available, for example the LG G7.

There are also some bootloader exploits such as [CVE-2020-12753] ([PoC]) that allow bootloader unlock as well.


***
Authored by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439), [DiabloSat](https://github.com/progzone122)<br/>

[announcement-archive]:https://www.reddit.com/r/LineageOS/comments/r961u3/termination_of_lg_mobile_developer_website/
[t-mobile-unlock]:https://xdaforums.com/t/unlock-bootloader-tmo.3578099/
[install guides]:https://wiki.lineageos.org/devices/d852/install/#installing-a-custom-recovery-using-dd

[CVE-2020-12753]:https://douevenknow.us/post/619763074822520832/an-el1el3-coldboot-vulnerability?

[PoC]:https://github.com/shinyquagsire23/CVE-2020-12753-PoC

[TMO Fastboot commands removed]:https://xdaforums.com/t/v10-bootloop-fix-lengthens-life.3694064/post-74461372
