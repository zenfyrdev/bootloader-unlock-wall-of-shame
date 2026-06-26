# Xiaomi/Redmi/POCO

- Verdict: **⛔ Avoid!**
- Verdict: **🍅 Terrible!** (Unisoc)

In the past, Xiaomi allowed most of its devices to be unlocked after a period of 7+ days (depending on how new the device is).

With the launch of Xiaomi's new Android fork, HyperOS, they have introduced a number of changes to the unlock process, with new device limits and Mi Account requirements.

Unisoc devices will never be unlockable, this is *not* Xiaomi's fault, Unisoc does not allow unlocking. 

## HyperOS

It is currently **impossible** to officially unlock Xiaomi phones from the China region, especially if the device was imported and you are outside China. They have removed the unlocking function in their community app.

With HyperOS, Xiaomi introduced an additional step to the unlock process. You can make the request for unlocking the device inside Developer Options, only after you have made another separate successful request inside the Xiaomi Community App.

For the international verson you can request unlocking in their Community App at 00:00 Chinese GMT+8 time.

If [xiaomiui.net][global-requirements] is to be believed, the requirements for the Community App request are as follows:
* Your Mi Account has been active for more than 30 days.
* Xiaomi Community App version 5.3.31 or above.
* [As of January 1st, 2025][updated-policies], Xiaomi only let you unlock 1 device per year. This requirement has also been extended to MIUI 14.

Additionally, [on xda forums][community-app-cap] people have found that there is a cap on the amount of people (belived to be around 50 people) who can request per day inside the Community App, and it gets filled pretty much instantly, so your only chance to make a successful request there is if you get lucky spamming the request at midnight, Beijing time ([GMT+8][gmt+8]).

### Workarounds

#### Snapdragon 8 Elite/8Gen3/8Gen2/8Gen1

All of those methods chain the QCOM SELinux bypass, and the Xiaomi MQSAS service privilege escalation vulnerabilities.

- Xiaomi 17 series, POCO F8 Ultra, Redmi K90 Pro Max with Security Patch before February 2026: [XDA](https://xdaforums.com/t/xiaomi17-series-and-pocof8ultra-redmi-k90-pro-max-unlock-bootloader-xiaomi8elite5seriesbootloader-unlock.4781439/)
- Xiaomi 13, 14, 15 series, MIX Flip 2, Pad 8 Pro, Pad 6S Pro, Redmi K90/K80/K70/K60 Pro with Security Patch before January 2026: [XDA](https://xdaforums.com/t/guide-breakthrough-free-offline-bootloader-unlock-for-cn-xiaomi15-pro-ultra-redmi-k90-sd-8-elite-also-support-8g2-8g3-no-cn-exam-required.4786790/)

It's theoretically possible to downgrade and unlock **non Kioxia UFS** devices using an EDL programmer and an engineering ABL: [XDA](https://xdaforums.com/t/unlock-bootloader-unbrick-xiaomi-8-elite-high-versions-auth-free-edl-firehose.4787466/)

### Other

* [AQLR][aqlr] The current bypass method, though you need to have your computer running at 00:00 Chinese ([GMT+8][gmt+8]) time. (The script is in AQLR.zip at the end of the post.)
* **MlgmXyysd** - MlgmXyysd, the developer of the original bootloader bypass script, has discovered a new vulnerability in Qualcomm devices that enables bootloader unlocking on most HyperOS 2 and 3 phones. You may contact her on CoolAPK; according to some sources.
* ~~Some users claim that visiting a Xiaomi store and asking a technician to downgrade the system version results in a temporary unlocked state. A few reported flashing their own system during this process.~~ 
* ~~[HyperSploit][hypersploit] is the newer option. This is a simple to use program with no external dependencies.~~ Confirmed as patched as of HyperOS version 2.0.203.0. Still works on old versions.
* ~~[Xiaomi-HyperOS-BootLoader-Bypass][xiaomi-hyperos-bootLoader-bypass] is the original proof of concept, but it's written in PHP and it's cumbersome to set up.~~ Same as above.

At the very end of the unlock process, [offici5l][offici5l]'s Python [MiUnlockTool][py-MiUnlockTool] can be used instead of the official Windows only [Mi Unlock][MiUnlock].

### Further Reading

- [Xiaomi BootLoader Questionnaire Questions](https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire) – community-collected notes and exam details. 

## MIUI 14 and below

> [!NOTE]
>On [Bilibili](https://www.bilibili.com/video/BV15Ut2z5Epo/?spm_id_from=333.1387.search.video_card.click&vd_source=96eca9b96bc62dc161f76ff2ff1fc1f3) some channels claim that that Xiaomi verification server has been shutdown.

You should be able to use the "normal" unlock process, without the Community app.

* Ensure a Xiaomi account was logged in on the device in the Settings app
* Go to Developer Options > Mi Unlock Status and press the button to request your device to be unlocked in the Xiaomi servers
* Then after 7+ days you can use the [official Mi Unlock][MiUnlock] for Windows or [offici5l][offici5l]'s Python [MiUnlockTool][py-MiUnlockTool] which will check those servers to see if a request has been made for that specific device and allow you to unlock it.

### Workarounds

EDL based unlock tool for Xiaomi Mi A1 and maybe all MSM89** manufactured before 2018:<br/>
[EDLUnlock](https://github.com/Giovix92/EDLUnlock)

### Further Reading

Look here if you want to learn about how Xiaomi's bootloader used to work: [Xiaomi-bootloader] <br/>
Alternative tools instead of Mi Flash Unlock: [Awesome Xiaomi BootLoader Unlock](https://github.com/topminipie/awesome-xiaomi-bootloader-unlock)


## Android One

* [**🔓️ Unlock Guide**](../../misc/generic-unlock.md)

Devices shipping with Android One do NOT have any unlock requirements. They follow the standard Android unlock process.

***
Updated info provided by [n1ses](https://github.com/n1ses) & [Crimson Fork/🌌🏳️‍⚧️&ΘΔ](https://cf.spaceport.nexus)  & [Mluo2011](https://github.com/Mluo2011) <br/>
Authored by [zenfyr](https://zenfyr.dev).

[hypersploit]:https://github.com/TheAirBlow/HyperSploit
[xiaomi-hyperos-bootLoader-bypass]:https://github.com/MlgmXyysd/Xiaomi-HyperOS-BootLoader-Bypass
[bootloader-unlock-block-mainland-china]:https://xiaomitime.com/bootloader-unlocking-comes-to-an-end-with-xiaomi-hyperos-2-0-12926
[bootloader-unlock-block-mainland-china-alt]:https://xiaomi.eu/community/threads/right-now-is-there-any-way-to-unlock-the-bootloader-on-chinese-versions-of-xiaomi-devices.73029/#post-726609
[bootloader-unlock-block-global]:https://x.com/chunvn8888/status/1841901853073953254
[global-requirements]:https://xiaomiui.net/how-unlock-bootloader-xiaomi-hyperos-53493
[Xiaomi-bootloader]:https://github.com/lrh2000/Xiaomi-bootloader
[yo-dawg-meme]:https://i.kym-cdn.com/photos/images/small/000/001/122/xzibit-happy.jpg "I heard you liked unlock requests…"
[community-app-cap]:https://xdaforums.com/t/application-quota-limit-reached.4695764
[updated-policies]:https://xiaomitime.com/xiaomi-global-bootloader-unlock-policy-has-changed-20295
[other requirements]:https://xiaomitime.com/xiaomi-restricts-bootloader-unlocking-with-new-180-day-rule-23160
[aqlr]:https://xdaforums.com/t/how-to-unlock-bootloader-on-xiaomi-hyperos-all-devices-except-cn.4654009/post-89311595
[gmt+8]:https://time.is/GMT%208
[offici5l]:https://offici5l.github.io
[py-MiUnlockTool]:https://github.com/offici5l/MiUnlockTool
[MiUnlock]:https://en.miui.com/unlock/download_en.html
