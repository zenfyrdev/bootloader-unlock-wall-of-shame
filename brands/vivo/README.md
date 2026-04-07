# Vivo/IQOO

- Verdict: **🍅 Terrible!**

The BBK* family has an unlocking problem. If in case of OPPO/Realme they at least offer an app in some regions, Vivo is locked completely.

Well, that is, if [xdaforums.com][BBK Fastboot] doesn't apply to you.

On pre-May 2022 firmware. I believe these methods *were* ~universal, but proceed with caution:

* Vivo x70 Pro+: [xdaforums.com][Vivo x70 Pro+]
* Vivo Y31 2021: [xdaforums.com][Vivo x70 Pro+]

There is also a chance that your device is vulnerable to one of the MTK or Unisoc [exploits](../../README.md#universal-soc-based-methods).

## Magisk
Vivo devices have kernel-level patches to block the `su` binary, so to use Magisk you should flash this modified version with `suu`. This only applies on devices which run Funtouch, for devices which run OriginOS (mainly their Chinese market devices), while the bootloader is still not unlockable, `su` is not blocked.
- [Magisk][patched-magisk]
- [Magisk Delta][patched-magisk-delta]

\* BBK Electronics was deregistered as a company on 7 April 2023.

***
Authored by [zenfyr](https://zenfyr.dev).

[BBK Fastboot]:https://xdaforums.com/t/how-to-unlock-bootloader-of-vivo-phones.3686690/
[Vivo x70 Pro+]:https://xdaforums.com/t/vivo-x70-pro-bootloader-unlock-how-to-guide.4444989/
[Vivo Y31 2021]:https://xdaforums.com/t/unlocking-bootloader-rebooting-in-edl-without-testpoint-vivo-y31-2021.4440801/
[patched-magisk]:https://github.com/4accccc/vivo-Magisk-suu/
[patched-magisk-delta]:https://github.com/4accccc/vivo-Magisk-Delta-suu
