# Fairphone

- Verdict: **⚠️ Proceed with caution!**

With firmware [FP3.6.A.040.2] on the Fairphone 3, with firmware [FP4.QREL.15.17.2] on the Fairphone 4, with firmware [FP5.VT2X.C.107] on the Fairphone 5 and with firmware [FP6.QREL.16.69.0] on the Fairphone (Gen. 6), Fairphone switched to the [standard unlock procedure](../../misc/generic-unlock.md). The OEM unlock option still requires an internet connection to verify the request.

All Fairphones after 2 require you to request a code from [this][unlock-website] website to enable OEM unlock. There is nothing stopping them from requiring an account and having device unlock limits in the future. This is "proceed with caution" after all.

Not very fair in my opinion, but whatever fairs your phone.

A [workaround] exists to avoid official server by using mitmproxy to authorize unlock, because there is no cryptographic signature, only HTTP status code.

They also [broke Verified Boot][verified-boot], lol

***
Authored by [zenfyr](https://zenfyr.dev).

[FP3.6.A.040.2]:https://forum.fairphone.com/t/software-update-fp3-6-a-040-2/130354
[FP4.QREL.15.17.2]:https://forum.fairphone.com/t/software-update-fp4-qrel-15-17-2-20260415141502/132010
[FP5.VT2X.C.107]:https://forum.fairphone.com/t/software-update-fp5-vt2x-c-107-20260609/132531
[FP6.QREL.16.69.0]:https://forum.fairphone.com/t/software-update-fp6-qrel-16-69-0-20260430160633/131953
[unlock-website]:https://shop.fairphone.com/bootloader-unlocking-code-for-fairphone
[verified-boot]:https://forum.fairphone.com/t/bootloader-avb-keys-used-in-roms-for-fairphone-3-4/83448/4
[workaround]:https://www.datenrei.ch/blog/2024/05/25/fp-oem-unlock-all.html
