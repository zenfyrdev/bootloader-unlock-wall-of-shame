# Xiaomi/Redmi/POCO

- Verdict: **⛔ Avoid!**
- Verdict: **🍅 Terrible!** (Unisoc)

In the past, Xiaomi allowed most of its devices to be unlocked after a period of 7+ days (depending on how new the device is).

With the launch of Xiaomi's new Android fork, HyperOS, they have introduced a number of changes to the unlock process, with new device limits and Mi Account requirements.

Look here if you want to learn about how Ximi's bootloader works: [Xiaomi-bootloader]

Unisoc devices will never be unlockable, this is *not* Xiaomi's fault, Unisoc does not allow unlocking.

# China
**Note**

The specifics of what can and cannot be done change over time, and different sources may claim different things depending on the time period.



### Devices running HyperOS 2 (China region)

It is currently **impossible** to unlock Xiaomi phones from the China region, especially if the device was imported and you are outside China. They have removed the unlocking function in their community app.

### Workarounds (use at your own risk)
- **Bootloader Bypass tools**  
  - [Xiaomi-HyperOS-BootLoader-Bypass](https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire) – Original PoC (PHP, cumbersome to set up)  
  - **AQLR** – Script-based, requires running at **00:00 China time** on PC (Doesn't work in china)
  - **HyperSploit** – User-friendly program, patched as of **HyperOS 2.0.203.0**, works only on older builds - Can bypass the 30 days old account requirement.
  - **MlgmXyysd** - MlgmXyysd, the developer of the original bootloader bypass script, has discovered a new vulnerability in Qualcomm devices that enables bootloader unlocking on most HyperOS 2 and 3 phones. You may contact her on CoolAPK; according to some sources, she charges 600 per unlocking.
- These tools try to exploit a vulnerability in the Community App request step so you can continue the 7-day waiting process and then unlock with Xiaomi’s official tool.  
- ⚠️ **Risks**: Using bypasses may get your device or account banned by Xiaomi.  

### Other reports
- Some users claim that visiting a Xiaomi store and asking a technician to downgrade the system version results in a temporary unlocked state. A few reported flashing their own system during this process — **Basically impossible** due to Xiaomi now using A/B flashing



### Devices running HyperOS 1
- Some may still be unlockable using bypass tools.  
- However, success is not guaranteed and bans are possible.  



### Devices running MIUI 14 and below
- These devices generally still support the **“classic” unlock process** (Mi Account login → Developer Options request → wait ~7 days → Mi Unlock tool), without requiring the Community App exam.  



### Timeline & Reports
- The last official day to submit unlock requests via the old form was reportedly **September 9, 2024**.  
- Xiaomi has hinted in the Community App that the service *may return in 2025*, but similar promises have not been fulfilled in the past.  
- Multiple forum posts suggest that **only users physically located in China, with Level 5 accounts, and valid Chinese ID can currently unlock**. Others sometimes resort to paid third-party services, though results vary.
- In **1/1/2026** Xiaomi offically remove the unlocking function from their community app.
- On **2/1/2026** MlgmXyysd the devloper of the orginal bootloader bypass claim she had found a way to unlock Qualcomm devices using a unknown vulnerability



📖 **Further Reading:**  
- [Xiaomi BootLoader Questionnaire Questions](https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire) – community-collected notes and exam details.  

### Global

> [!WARNING]
> Since October 2024 [there have been rumors][bootloader-unlock-block-global] that Xiaomi will kill bootloader unlocking on the Global market, after having done so for the China market.
>
> If you own a Xiaomi device and your warranty has ended or you don't care for it, you should unlock your device while you can.

### Devices running HyperOS (even if they were upgraded to it from MIUI)

First of all we should clear up something: HyperOS is essentially a new marketing term for what would've been MIUI 15. So it's still a vendor skin/theming engine on top of Linux-based Android, it's just called HyperOS instead of MIUI as it used to be called.

Secondly: One might remember how, in order to unlock the device back in the good old MIUI days, you would:

* Ensure a Xiaomi account was logged in on the device in the Settings app
* Go to Developer Options > Mi Unlock Status and press the button to request your device to be unlocked in the Xiaomi servers
* Then after 3 days you can use the [official Mi Unlock][MiUnlock] for Windows or [offici5l][offici5l]'s Python [MiUnlockTool][py-MiUnlockTool] which will check those servers to see if a request has been made for that specific device and allow you to unlock it.

Not straightforward or fast, but doable.
WELL:

With HyperOS Xiaomi essentially makes the second stop more compilated.

That is, you can only make the request for unlocking the device inside Developer Options, ONLY AFTER you have made another SEPARATE successful request inside the Xiaomi Community App, which will then allow you to make the ACTUAL first request you wanted inside the Developer Settings (![yo dawg…][yo-dawg-meme])

If [xiaomiui.net][global-requirements] is to be believed, the requirements for the Community App request are as follows:
* Your Mi Account has been active for more than 30 days.
* Xiaomi Community App version 5.3.31 or above.
* Xiaomi has [updated their policies][updated-policies], further restricting bootloader unlocking. As of January 1st, 2025, they only let you unlock 1 device per year. *What a good way to start the year, right?* This requirement has also been added to MIUI 14.

And it gets even better! As people have found it the hard way [in the xda forums][community-app-cap], there is a cap on the amount of people who can request per day inside the Community App, and it gets filled pretty much instantly, so your only chance to make a successful request there is if you get lucky spamming the request at midnight, Beijing time (or whatever that is in your timezone).

As such, for as long as the option is available, you'll skip this community BS and use the bypass methods:

* [AQLR][aqlr] The current bypass method, though you need to have your computer running at 00:00 Chinese ([GMT+8][gmt+8]) time. (The script is in AQLR.zip at the end of the post.)
  * At the very end, [offici5l][offici5l]'s Python [MiUnlockTool][py-MiUnlockTool] can be used instead of the official Windows only [Mi Unlock][MiUnlock].
* ~~[HyperSploit][hypersploit] is the newer option. This is a simple to use program with no external dependencies.~~ Confirmed as patched as of HyperOS version 2.0.203.0. Still works on old versions.
* ~~[Xiaomi-HyperOS-BootLoader-Bypass][xiaomi-hyperos-bootLoader-bypass] is the original proof of concept, but it's written in PHP and it's cumbersome to set up.~~ Same as above.

This will (for now) allow you to continue with the last of the **bad old MIUI days** steps, where you wait for 3 (used to be 7) days and can then unlock your phone successfully.
Do NOT make a new request by pressing the button in the Settings app as that will undo you bypass (hypersploit, MiUnlockTool and Mi Unlock also mention this to you). The tool will make the needed request itself.
The only thing you need to do is use Xiaomi's [official Mi Unlock][MiUnlock] or [offici5l][offici5l]'s [Python script][py-MiUnlockTool] after 3 days.

### Devices running MIUI 14 and below

You should be able to use the "normal" unlock process by itself, wihtout the community app BS
(the one descibed in the "bad old MIUI days" section above).

## Workarounds
On some old Devices 9008 or MTK client might be able be unlock.
Xiaomikey could also work on some devices.


## Android One

* [**🔓️ Unlock Guide**](../../misc/generic-unlock.md)

Devices shipping with Android One do NOT have any unlock requirements. They follow the standard Android unlock process.

***
Updated info provided by [n1ses](https://github.com/n1ses) & [Crimson Fork/🌌🏳️‍⚧️&ΘΔ](https://cf.spaceport.nexus)<br/>
Authored by [melontini](https://github.com/melontini).

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
