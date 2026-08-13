# Xiaomi/Redmi/POCO

- Verdict: **🍅 Just terrible!**
- Verdict: **⛔ Avoid at all costs!** (Unisoc)

In the past, Xiaomi allowed most of its devices to be unlocked after a period of 7+ days (depending on how new the device is).

With the launch of Xiaomi's new Android fork, HyperOS, they have introduced a number of changes to the unlock process, with new device limits and Mi Account requirements.

Unisoc devices will never be unlockable, this is *not* Xiaomi's fault, Unisoc does not allow unlocking.

## Android One

* [**🔓️ Unlock Guide**](../../misc/generic-unlock.md)

Devices shipping with Android One do NOT have any unlock requirements listed below. They follow the standard Android unlock process.

## Device unlock requirements

Devices shipping with MIUI or HyperOS require activating your phone with Xiaomi servers before allowing unlocking. You can only unlock one phone in 30 days and four phones in a year.

After enabling Developer options, go to Settings > Additional settings > Developer options, enable OEM Unlock and go to Device Unlock Status page, and if it shows "Locked" then you can proceed pressing "Add account and device" button to initiate the process.

Doing these won't unlock your device immediately, but will grant you a permission to unlock in the end. So, to be able to eligible for unlocking, you will be asked to do these steps.

Xiaomi will let you know what is required right now when you press "Add account and device", but to explain fully in order, it tells you to do:

* Your device linked with a Xiaomi Account that is in a good standing (even better if it is not a recently created account)
* A SIM card inserted in with an active data plan (if device has SIM slot)
* Wi-Fi is disabled and mobile data is enabled (if device has SIM slot)
* If running HyperOS:
    * See [new HyperOS requirements](#hyperos-specific) down below

When you complete all above steps, pressing "Add account and device" button now should say "Added successfully" message.

To actually *perform* the unlocking, you will need to use [Mi Unlock][miunlock] tool for Windows and follow prompts to enter fastboot mode and connect your device. If you cannot or don't want to use official tool, you can also use alternative tools such as [offici5l][offici5l]'s [MiUnlockTool][py-miunlock] made in Python.

The unique key is to unlock the bootloader of your device is retrieved from Xiaomi servers, but there is a server-side (thus no tool can't bypass server time) countdown that will start running only after completing all steps above. For the most cases, the countdown is 3 days (= 72 hours) for HyperOS and 7 days (= 168 hours) for MIUI, but there are some reports people being forced to wait even more, such as 14 or 30 days instead.

You can continue using your device as usual and check with the unlock tool anytime to see how much time is left. Meanwhile, DON'T remove your Xiaomi account or factory reset your phone, doing these may result in the countdown being reset to what it was initially.

> [!NOTE]
> For MIUI devices (not HyperOS), some channels on [Bilibili][bilibili-shutdown] claim that that Xiaomi verification server has been shutdown.

## HyperOS specific

It is currently **impossible** to officially unlock Xiaomi phones from the China region, especially if the device was imported and you are outside China. They have removed the unlocking function in their community app.

With HyperOS, Xiaomi introduced an additional step to the unlock process. You can make the request for unlocking the device inside Developer Options, only after you have made another separate successful request inside the [Xiaomi Community App.][mi-community-app]

For the international version you can request unlocking in their Community App at 00:00 Beijing (Chinese) [GMT+8][gmt+8] time.

The [requirements for the Community App][global-requirements] request are as follows:

* Your Mi Account has been active for more than 30 days.
* Xiaomi Community App version 5.3.31 or above.
* [As of January 1st, 2025][updated-policies], Xiaomi only let you unlock 1 device per year. This requirement has also been extended to MIUI 14.
* Make sure to select "Global" region in Xiaomi Community app to see "Unlock bootloader" section under "Me" tab.

Additionally, [on XDA forums][community-app-cap] people have found that there is a cap on the amount of people (belived to be around 50 people) who can request per day inside the Community App, and it gets filled pretty much instantly, so your only chance to make a successful request there is if you get lucky spamming the request at midnight, Beijing time ([GMT+8][gmt+8]).

There is a [AQLR][aqlr] (abbreviation of "application quota limit reached") script to do that automatically, so it would send a request to Xiaomi just before entering a new day in China, and you can have your computer running that script 7/24.

> [!WARNING]
> Even if it appears like you missed the today's quota, Xiaomi may report "application quota limit reached" [by a mistake even though you actually did placed in the quota][quota-error-problem]. So the only way is to be sure about that is to pressing "Add account and device" in Device Unlock Status page in Settings.

## Workarounds & Exploits

### Snapdragon 8 Elite/8Gen3/8Gen2/8Gen1

All of those methods chain the QCOM SELinux bypass, and the Xiaomi MQSAS service privilege escalation vulnerabilities.

- Xiaomi 17 series, POCO F8 Ultra, Redmi K90 Pro Max with Security Patch before February 2026, [see here][xda-qcom-1]
- Xiaomi 13, 14, 15 series, MIX Flip 2, Pad 8 Pro, Pad 6S Pro, Redmi K90/K80/K70/K60 Pro with Security Patch before January 2026, [see here][xda-qcom-2]

It's theoretically possible to downgrade and unlock **non Kioxia UFS** devices [using an EDL programmer and an engineering ABL][firehose] too.

### MSM89xx

[EDLUnlock][edl-unlock], an EDL unlock tool for Xiaomi Mi A1 and maybe all MSM89xx manufactured before 2018.

### Others

* **MlgmXyysd** - MlgmXyysd, the developer of the original bootloader bypass script, has discovered a new vulnerability in Qualcomm devices that enables bootloader unlocking on most HyperOS 2 and 3 phones. You may contact her on CoolAPK; according to some sources.
* ~~Some users claim that visiting a Xiaomi store and asking a technician to downgrade the system version results in a temporary unlocked state. A few reported flashing their own system during this process.~~ 
* ~~[HyperSploit][hypersploit] is the newer option. This is a simple to use program with no external dependencies.~~ Confirmed as patched as of HyperOS version 2.0.203.0. Still works on old versions.
* ~~[Xiaomi-HyperOS-BootLoader-Bypass][xiaomi-hyperos-bootLoader-bypass] is the original proof of concept, but it's written in PHP and it's cumbersome to set up.~~ Same as above.

## Further reading

- [Xiaomi BootLoader Questionnaire Questions][bootloader-questionnaire] - community-collected notes and exam details. 
- [Awesome Xiaomi Bootloader Unlock][awesome-bootloader-unlock]
- [Some research about the bootloader used in Xiaomi phones][xiaomi-bootloader]

And, Xiaomi's "reasoning" on [why they do this:][official-guide]

> **Isn't locking the bootloader against Xiaomi's 'geek' spirit?**
>
> Locking the bootloader is aimed to provide a better user experience, which we've been trying to do the whole time. In the meantime, we've provided an unlocking tool for senior users who know their ways around flashing and tweaking their devices.
>
> The unlocking procedure will need internet access to get the unlocking password. Also, the Xiaomi Account logged in on the Xiaomi phone and the unlocking tool needs to be the same. Otherwise, the unlocking request will be denied. This will ensure that ill-intentioned people will not get access to your personal data.

***
Updated info provided by [n1ses](https://github.com/n1ses) & [Crimson Fork/🌌🏳️‍⚧️&ΘΔ](https://cf.spaceport.nexus)  & [Mluo2011](https://github.com/Mluo2011) & [ysfchn](https://ysfchn.com) <br/>
Authored by [zenfyr](https://zenfyr.dev).

[official-guide]: https://new.c.mi.com/global/post/101245
[hypersploit]: https://github.com/TheAirBlow/HyperSploit
[xiaomi-hyperos-bootLoader-bypass]: https://github.com/MlgmXyysd/Xiaomi-HyperOS-BootLoader-Bypass
[bootloader-unlock-block-mainland-china]: https://xiaomitime.com/bootloader-unlocking-comes-to-an-end-with-xiaomi-hyperos-2-0-12926
[bootloader-unlock-block-mainland-china-alt]: https://xiaomi.eu/community/threads/right-now-is-there-any-way-to-unlock-the-bootloader-on-chinese-versions-of-xiaomi-devices.73029/#post-726609
[bootloader-unlock-block-global]: https://x.com/chunvn8888/status/1841901853073953254
[global-requirements]: https://new.c.mi.com/global/post/673501
[xiaomi-bootloader]: https://github.com/lrh2000/Xiaomi-bootloader
[yo-dawg-meme]: https://i.kym-cdn.com/photos/images/small/000/001/122/xzibit-happy.jpg "I heard you liked unlock requests…"
[community-app-cap]: https://xdaforums.com/t/application-quota-limit-reached.4695764
[updated-policies]: https://xiaomitime.com/xiaomi-global-bootloader-unlock-policy-has-changed-20295
[other-requirements]: https://xiaomitime.com/xiaomi-restricts-bootloader-unlocking-with-new-180-day-rule-23160
[aqlr]: https://xdaforums.com/t/how-to-unlock-bootloader-on-xiaomi-hyperos-all-devices-except-cn.4654009/post-89311595
[mi-community-app]: https://play.google.com/store/apps/details?id=com.mi.global.bbs
[quota-error-problem]: https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame/issues/287
[xda-qcom-1]: https://xdaforums.com/t/xiaomi17-series-and-pocof8ultra-redmi-k90-pro-max-unlock-bootloader-xiaomi8elite5seriesbootloader-unlock.4781439/
[xda-qcom-2]: https://xdaforums.com/t/guide-breakthrough-free-offline-bootloader-unlock-for-cn-xiaomi15-pro-ultra-redmi-k90-sd-8-elite-also-support-8g2-8g3-no-cn-exam-required.4786790/
[gmt+8]:https://time.is/GMT%208
[offici5l]:https://offici5l.github.io
[py-miunlock]:https://github.com/offici5l/MiUnlockTool
[miunlock]:https://en.miui.com/unlock/download_en.html
[bilibili-shutdown]: https://www.bilibili.com/video/BV15Ut2z5Epo/?spm_id_from=333.1387.search.video_card.click&vd_source=96eca9b96bc62dc161f76ff2ff1fc1f3
[firehose]: https://xdaforums.com/t/unlock-bootloader-unbrick-xiaomi-8-elite-high-versions-auth-free-edl-firehose.4787466/
[edl-unlock]: https://github.com/Giovix92/EDLUnlock
[bootloader-questionnaire]: https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire
[awesome-bootloader-unlock]: https://github.com/topminipie/awesome-xiaomi-bootloader-unlock