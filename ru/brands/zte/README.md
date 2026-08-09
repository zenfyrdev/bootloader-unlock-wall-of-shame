# ZTE/nubia/Redmagic

> 🧹 На этой странице не хватает информации!

- Вердикт: **🍅 Просто ужасно!**
- Вердикт: **🍅 Просто ужасно!** (Unisoc)

Устройства nubia на Snapdragon можно разблокировать командой `fastboot oem nubia_unlock NUBIA_MODEL` (например, для модели NX609J: `fastboot oem nubia_unlock NUBIA_NX609J`). Новые устройства ZTE также можно разблокировать командой `fastboot flashing unlock`, но это часто ломает сканер отпечатков. Устройства на Unisoc никогда не будут разблокируемы.

Старые устройства (до Android 8):<br/>
[xdaforums.com][pre-android-8]

Устройства до Android 11 с инженерной прошивкой:<br/>
[xdaforums.com][until-android-11-few-models]

Возможно, ваше устройство уязвимо к одному из [эксплойтов](../../README.md#%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-soc-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D1%8B) MTK или Unisoc.

***
Дополнительная информация: [Skorpion96](https://github.com/Skorpion96).
Автор: [zenfyr](https://zenfyr.dev).

[pre-android-8]:https://xdaforums.com/t/bootloader-unlocking-on-older-qualcomm-zte-devices-devinfo-partition-modification.4100897/
[until-android-11-few-models]:https://xdaforums.com/t/zte-blade-a5-2019-2020-etc-root-guide-locked-bootloader-valid-for-all-unisoc-zte-models-with-an-engineering-firmware.4612391/
[unisoc-cve]:https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader/releases/tag/1.72
