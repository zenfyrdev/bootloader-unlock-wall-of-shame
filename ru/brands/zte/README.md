# ZTE/nubia/Redmagic

> 🧹 На этой странице не хватает информации!

- Вердикт: **🍅 Просто ужасно!**
- Вердикт: **⛔ Избегать любой ценой!** (Unisoc)

## Новые устройства (Snapdragon 8850/8750) 
Новые устройства на Snapdragon можно разблокировать с помощью эксплойта, включая серии Redmagic 11 и 10, Nubia Z80 и Z70 и, возможно, некоторые другие (точный список неясен). Для некоторых устройств требуется определённый патч безопасности, для других — нет. https://xdaforums.com/t/red-magic-11-pro-guide-bootloader-unlock-free-also-support-rm10-pad3pro-z70u-z80u-unlock-zte-family-toolbox.4780930/. Однако разработчик недавно подвергся пристальному вниманию и критике, поэтому маловероятно, что будущие устройства будут поддерживаться (RM12, Z90 и т. д.).

Разблокировка часто ломает сканер отпечатков пальцев, но для некоторых устройств предоставлен обход.

Устройства на Unisoc никогда не будут разблокируемы — это *не* вина ZTE, Unisoc не разрешает разблокировку.

## Старые устройства
Устройства nubia на Snapdragon можно разблокировать командой Fastboot `fastboot oem nubia_unlock NUBIA_MODEL` (например, если номер модели вашего телефона NX609J, команда будет `fastboot oem nubia_unlock NUBIA_NX609J`). Устройства ZTE также можно разблокировать стандартной командой `fastboot flashing unlock`.

Что касается устройств ZTE, не относящихся к nubia:

Старые устройства (до Android 8):<br/>
[xdaforums.com][pre-android-8]

Устройства до Android 11 с инженерной прошивкой:<br/>
[xdaforums.com][until-android-11-few-models]

Возможно, ваше устройство уязвимо к одному из [эксплойтов](../../README.md#универсальные-soc-методы) MTK или Unisoc.

К слову, по ссылке на A11 есть подборка приложений для получения системного шелла, но они, скорее всего, сработают только на старых моделях.

***
Новые телефоны добавлены xMicro (9/5).
Дополнительная информация предоставлена [Skorpion96](https://github.com/Skorpion96).
Автор: [zenfyr](https://zenfyr.dev).

[pre-android-8]:https://xdaforums.com/t/bootloader-unlocking-on-older-qualcomm-zte-devices-devinfo-partition-modification.4100897/
[until-android-11-few-models]:https://xdaforums.com/t/zte-blade-a5-2019-2020-etc-root-guide-locked-bootloader-valid-for-all-unisoc-zte-models-with-an-engineering-firmware.4612391/
[unisoc-cve]:https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader/releases/tag/1.72
