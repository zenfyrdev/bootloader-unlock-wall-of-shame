# 🔓️ Samsung Unlock Guide

- Difficulty: **Easy 📗** (International models running One UI 7 or earlier)
- Difficulty: **Impossible ❌** (North American models, or any Samsung running One UI 8 or later)

> [!CAUTION]
> Read in full before you act!

The standard unlocking process for Samsung is to enable OEM Unlocking, then go to the "Warning!" screen and hold down a button to unlock the bootloader. On older devices (prior to 2019), all you have to do is enable OEM unlocking, and your bootloader is unlocked, no data wipe required on older devices.

## Requirements

- A supported Samsung device
- Ability to follow simple instructions.

> [!NOTE]
> This guide does not work with most North American Samsungs!<br/>
> The only exceptions are devices prior to the S7, and Exynos devices.<br/>
> This will not work on One UI 8 or later! Samsung has completely removed the ability to unlock starting with One UI 8.

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


## Troubleshooting

> OEM Unlock is missing or greyed out.

Your device is locked to a carrier that restricts unlocking, you have an American device, or you're running One UI 8 or later. In some edge cases (e.g. on the 2015 Galaxy Tab A 8.0) this option won't be present as the bootloader ships unlocked, but this is very rare.

> When I try to hold the button combination, my phone just boots normally.

Some Samsung devices have key combinations that are different from their normal ones, you'll have to Google your device model to see the exact combination for your device.
