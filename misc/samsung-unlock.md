# 🔓️ Samsung Unlock Guide

- Difficulty: **Easy 📗** (International models running One UI 7 or earlier — bootloader unlocking generally possible)
- Bootloader unlocking: **Impossible ❌** (North American models, or devices where Samsung removed the unlock option on One UI 8+)
- Upgrade from One UI 7 → One UI 8: **Possible ⚠️** (see upgrade section below to preserve unlockability)

> [!CAUTION]
> Read in full before you act!

The standard unlocking process for Samsung is to enable OEM Unlocking, then go to the "Warning!" screen and hold down a button to unlock the bootloader. On older devices (prior to 2019), all you have to do is enable OEM unlocking, and your bootloader is unlocked, no data wipe required on older devices.

## Requirements

- A supported Samsung device
- Ability to follow simple instructions.

> [!NOTE]
> This guide does not work with most North American Samsungs!<br/>
> The only exceptions are devices prior to the S7, and Exynos devices.<br/>
> While direct bootloader unlocking is impossible on many One UI 8+ devices or North American variants, upgrading from One UI 7 to One UI 8 is still possible — but only if you follow the specific firmware update rules in the section below.

## OEM Unlocking

To enable OEM Unlocking, you must first gain access to Developer Options.

> [!NOTE]
> OEM Unlocking allows you to unlock the bootloader, but it also disables Google's factory reset protection.

On Samsung devices, you will need to go to "About phone" in the Settings app to unlock the dev options, 
in this menu look for "Build Number", 
now tap the button several times until a confirmation toast/prompt appears.

Now you can search for Developer options and from there enable OEM Unlocking.

## Download mode
Power off your phone. The next procedure will depend on what buttons you device has
- Devices with home button: Hold Power+Volume Down+Home until phone goes to the Warning screen
- Devices with Bixby button: Hold Power+Volume Down+Bixby until phone goes to the Warning screen.
- Devices with neither buttons: Hold down Volume Down+Volume Up, connect phone to computer, continue holding buttons until you see the Warning screen.

The next step will depend on what your device's warning screen looks like.
![image](https://github.com/user-attachments/assets/11dcf926-989f-420d-b8f2-29c63bb5dc58)

If it's variation 1 or 2, your bootloader is already unlocked. If you have variation 3, hold down volume up until it asks if you'd like to unlock the bootloader, then press volume up again to wipe data and unlock bootloader. 

## Upgrading from One UI 7 → One UI 8

Upgrading your device from One UI 7 to One UI 8 can be done, but maintaining an unlocked bootloader requires following strict flashing rules. These steps are device- and firmware-specific and carry risk — they do not guarantee success.

- Before attempting to update to One UI 8, update the following firmware packages first: AP, CP and CSC (If you have a custom kernel, vbmeta or something then unpack AP and replace with your files and flash them).
- Under NO CIRCUMSTANCES flash the BL package as-is.
- If an update bundle contains a BL package, unpack it and flash every component from that bundle except sboot.bin.lz4 — do NOT flash sboot.bin.lz4.

If you are unsure what any of the above means, just stop or ask someone

## Troubleshooting

> OEM Unlock is missing or greyed out.

Your device is locked to a carrier that restricts unlocking, you have an American device, or you're running One UI 8 or later.

> When I try to hold the button combination, my phone just boots normally.

Some Samsung devices have key combinations that are different from their normal ones, you'll have to Google your device model to see the exact combination for your device.
