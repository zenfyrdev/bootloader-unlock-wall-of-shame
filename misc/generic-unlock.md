# 🔓️ Generic Unlock Guide

- Difficulty: **Easy 📗**

> [!CAUTION]
> Read in full before you act!

The standard unlocking process is to enable **OEM unlocking** from the developer options and then run some commands from fastboot.

## Requirements

- A device to which you can connect your patient.
- Ability to tweak terminal commands to fit your system.
- Ability to follow simple instructions.

> [!NOTE]
> This guide does not work with Unisoc/Spreadtrum devices!<br/>
> They require additional steps not mentioned here.

## Getting Ready

To unlock your phone, you have to download SDK Platform Tools.

Go to [developer.android.com](https://developer.android.com/tools/releases/platform-tools#downloads) and download the package for your OS (most likely Windows) and extract the archive where appropriate. 
On Linux it may be better to use your distro's package manager, although the package may be quite old.

### Windows

On Windows, some devices might require special drivers. In these cases, Windows can download them automatically. 
Otherwise, go to [OEM USB Drivers](https://developer.android.com/studio/run/oem-usb) and search for your manufacturer. 
If your device isn't included in this list, you'll have to search for drivers yourself.

### Linux

> Should only happen when using the archive version.

If you run `./fastboot devices` now, you may get a `no permissions; see [http://developer.android.com/tools/device.html]` error.

One solution is to use `sudo`, `pkexec` or `run0`, 
but the correct way is to set up `udev` rules for the adb/fastboot binary to work. The procedure usually depends on the distribution.

## OEM Unlocking

To enable OEM Unlocking, you must first gain access to Developer Options.

> [!NOTE]
> OEM Unlocking allows you to unlock the bootloader, but it also disables Google's factory reset protection.

On almost all Android phones you will need to go to "About Device" or similar to unlock the dev options, 
in this menu look for "Build Number", 
now tap the button several times until a confirmation toast/prompt appears.

Now you can search for Developer options and from there enable OEM Unlocking.

## Fastboot

Now you need to restart your phone in Fastboot mode. 
This varies from device to device, but can usually be done by pressing and holding the power and volume down button while the phone is switched off. 
Another option is to use ADB:

```sh
adb reboot bootloader
```

To unlock the bootloader, you have to run the following commands in fastboot mode.

<details><summary>Almost all modern devices</summary>
<p>

```sh
fastboot flashing unlock
```

</p>
</details> 

<details><summary>Older devices</summary>
<p>

```sh
fastboot oem unlock
```

</p>
</details>

## Troubleshooting

> I cannot get into Fastboot.

If you cannot boot into Fastboot using the volume buttons, try the ADB command above. 
If the device still refuses to boot, your OEM may have restricted fastboot access, 
in which case you'll need to consult device-specific guides.

> I get `fastboot flashing unlock: FAILED (remote: Unrecognized command flashing unlock)` when I try to run the command.

Make sure the device is in Fastboot mode, not FastbootD. FastbootD is for other things.

If Fastboot still doesn't recognise your commands, 
your OEM may have removed the correct unlock command, 
in which case you'll need to consult device-specific guides.