# Apple

- Verdict: **🍅 Terrible!**

As expected, Apple does not allow bootloader unlocking, and never has. Most Apple devices also have an aggressive anti-rollback system, stopping you from downgrading to an older iOS version for jailbreaking purposes.

## Firmware signing
Apple has a server called "Tatsu Signing Server", typically shortened to TSS. When you try to install firmware on an Apple device, iTunes or Finder will send several things to TSS so it can generate a signed SHSH blob to allow the restore, the following being

- The Model ID, this tells it what device you have. For example, the global model of the iPhone 5s is iPhone6,2, the Wi-Fi only model of the iPad Air 3 is iPad11,3, the global model of the iPhone X is iPhone10,3, etc.
- The build ID, this identifies the exact build of iOS you are trying to install, iOS 14.3 is 18B92, iOS 10.3.3 is 14G60, etc.
- Your device's ECID, a string unique to every device, and what allows the SHSH blob to work on your device only. This cannot be spoofed as the ECID is burned into the CPU during manufacturing.
- The type of restore, which can either be an iTunes/Finder restore, which wipes all data on the device and reinstalls iOS, an iTunes/Finder update, which is updating the firmware from a computer, or an OTA update, which is the update being installed on-device. Each type of restore needs a different kind of SHSH blob.

Once the following data is sent, TSS will give one of three responses.

- Response 1: Firmware is being signed, the SHSH blob can be generated
- Response 2: Firmware is NOT signed, the SHSH blob CANNOT be generated.
- Response 3: Firmware is incompatible with your device, the SHSH blob CANNOT be generated.

If response 1 is received, then the process of creating a blob can continue, that goes as follows:

- Apple has a private key that no one else knows
- The bootROM on your device has a public key, which can verify if the firmware was made using Apple's private key.
- When response 1 is received, TSS takes the model ID, build ID, ECID and the restore type, and uses that to hash a file (SHA1 for all devices made prior to 2016, or SHA384 for devices made in 2016 or later, excluding the iPhone SE 1, first gen iPad Pro, and iPad 5 -- those use SHA1)
- The device takes that blob, uses the public key to verify it's an authentic Apple blob, and if it is, it then verifies if the blob has the same Model ID, build ID, device ECID and restore type, if so, the blob is saved to the device, and the restore can continue.

Firmware signing was only introduced in 2009 with the iPhone 3GS and "new bootrom" iPod Touch 2. If you have an iPhone 2G, iPhone 3G, iPod Touch 1 or "old bootrom" iPod Touch 2, the device does not have firmware signing and you can downgrade to whatever version you want.

Usually, Apple unsigns old versions 3-7 days after a new version comes out, however, there are some rare cases, for example, it isn't possible for iOS 5.0.x to directly OTA to iOS 7, for iOS 6 to directly OTA to iOS 9, or for iOS 7 to directly OTA to iOS 11, so for the iPhone 4S and older revisions of the iPad 2, iOS 6.1.3 is still signed, for the iPhone 4S, iPhone 5, iPad 2, iPad 3, iPad 4, iPad mini 1, and iPod Touch 5, iOS 8.4.1 is still signed, and for the iPhone 5s, iPad Air 1, and iPad mini 2, iOS 10.3.3 is still signed. However, you can't restore directly with iTunes or Finder to downgrade, as TSS will only provide the blob for OTA. [Legacy iOS Kit] is able to grab the OTA blob and restore with it using the checkm8 exploit, however. You can also spoof your iOS version by editing a plist file when jailbroken, however this method is unreliable and usually doesn't work anymore.

If your device has a bootROM exploit, you can extract the blob, and then use software such as [futurerestore] to restore to that version in certain cases, but Apple being Apple, added yet another thing to make downgrading more difficut, that being SEP:

### SEP
In the Apple A7 SoC, Apple introduced a coprocessor called the Secure Enclave Processor, typically shortened to SEP. It is used for data protection, touch ID and face ID, the SEP's purpose is to handle keys that are sensitive enough to require isolation from the rest of the device. The SEP's firmware is frequently updated, and the updates typically make it incompatible with older iOS versions, and the SEP has its own firmware signing process, so without a SEP exploit, you cannot downgrade to an older version without a SEP exploit, even if you have an SHSH blob and bootrom exploit. The SEP is present in all Apple devices made in 2013 or later (excluding the iPhone 5c, as the 5c uses the older Apple A6 SoC.). There are only two known SEP exploits, [blackbird], which affects the A8-A10 (2014-2016), and [hardbird], which affects the A7 (2013)

For devices using the Apple A9, Apple A10, or associated variants, you can use [turdus merula] to downgrade, untethered if you have SHSH blobs, otherwise a tethered downgrade. turdus merula uses the blackbird exploit. A8 is currently not supported.

## bootROM and iBoot exploits
The bootROM is an SoC-level code, and the first thing that runs on an Apple device upon boot, and the code is read-only. A bootROM exploit is the Apple equivelant of a hardware-level bootloader unlock exploit. However, the attack vector is very small, and only two have been found in the last ten years.

iBoot is Apple's bootloader. an iBoot exploit is Apple's equivelant of a software-level bootloader unlock exploit, however, since it's software level, and iBoot is usually updated in every iOS update, exploits are usually quickly patched and the last iOS version with a known iBoot exploit is 7.1.2, which released in 2014.
### checkm8
[checkm8] (CVE-2019-8900) was a bootROM exploit discovered in 2019, and from 2019 to 2026, it was the only bootROM exploit to affect 64-bit devices. It was the first major bootROM exploit discovery since 2010's limera1n. It is a very capable exploit, affecting all Apple SoCs from the A5 to the A11, meaning it affects all Apple devices made from 2011 to 2017, and also the iPad 6 (2018), iPad 7 (2019), and iPod Touch 7 (2019). The main part of the exploit also affects the A12 and A13, however the A12 patched a memory leak in DFU, which makes it impossible to actually execute the exploit, unless you leave your device in DFU mode for several months. checkm8 is used by many jailbreaks and iOS tools, including turdus merula, Legacy iOS Kit, checkra1n, palera1n, and even [Project Sandcastle], which allows you to run a very broken Android build on the iPhone 7. However, there are a number of issues with checkm8:
- It is a tethered exploit, so once you reboot or power off your phone, you'll have to connect to your computer to re-run the exploit.
- The exploit has absolutely zero support for Windows, you need to use macOS or Linux.
- checkm8 has an extremely high failure rate on AMD CPUs, most projects that use checkm8 tell you to not even bother if you're on AMD and to just get a cheap Intel system. AMD is the only brand affected, all other CPUs (x86 or ARM) work.
- If using a device with the Apple A5 (iPhone 4S, iPad 2, iPad 3, iPad mini 1 or iPod touch 5), you need an Arduino with a USB Host Shield to run checkm8, it won't work without it.
- If using a device with the Apple A7 (iPhone 5s, iPad Air 2, iPad mini 2 or iPad mini 3), exploiting on Linux almost always fails, you'll need to use macOS. A Hackintosh will work fine, as long as it has an Intel CPU.

### usbliter8
[usbliter8] is a bootROM exploit discovered in 2026, for the Apple A12, Apple A13, Apple S5, and their associated variants. As of right now, due to being a very new exploit, virtually nothing supports it, however it can be expected that jailbreaking tools will support usbliter8 in the future. usbliter8 requires an RP2350 based microcontroller, such as a Raspberry Pi Pico 2.

### Other exploits
checkm8 and usbliter8 are the only ones that applu to modern devices, so it's the only two that I'll go into detail on, but there are a number of other exploits, including alloc8 (iPhone 3GS), limera1n (iPod touch 3, and all Apple A4 devices.), 24Kpwn (old bootrom iPod touch 2) and Pwnage (iPhone 2G, iPod Touch 1 and iPhone 3G). For iBoot exploits, there's DRA (32-bit iOS 7.0-7.1.2), HFS Heap Buffer Overflow (iOS 5.0-5.1.1), usb_control_msg(0x21, 2) (iOS 3.1-3.1.2), and EVO (iOS 3.0).
***
Authored by [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>

[futurerestore]:https://github.com/futurerestore/futurerestore
[Legacy iOS Kit]:https://github.com/LukeZGD/Legacy-iOS-Kit
[turdus merula]:https://sep.lol/
[blackbird]:https://theapplewiki.com/wiki/Blackbird_Exploit
[hardbird]:https://theapplewiki.com/wiki/Hardbird_Exploit
[checkm8]:https://theapplewiki.com/wiki/Checkm8_Exploit
[Project Sandcastle]:https://projectsandcastle.org/
[usbliter8]:https://theapplewiki.com/wiki/Usbliter8_Exploit
