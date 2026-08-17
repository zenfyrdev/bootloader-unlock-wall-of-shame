# Vivo/IQOO

- Вердикт: **⛔ Избегать любой ценой!**

У семейства BBK* есть проблемы с разблокировкой. Если OPPO/Realme, по крайней мере, предлагают приложение в некоторых регионах, то Vivo полностью залочена.

Ну, то есть, если [xdaforums.com][BBK Fastboot] вам не подходит.

На прошивках до мая 2022 года. Я полагаю, что эти методы *были* почти универсальными, но действуйте осторожно:

* Vivo x70 Pro+: [xdaforums.com][Vivo x70 Pro+]
* Vivo Y31 2021: [xdaforums.com][Vivo x70 Pro+]

Также есть шанс, что ваше устройство уязвимо к одному из [эксплойтов](../../README.md#универсальные-soc-методы) для MTK или Unisoc.

## Magisk
На устройствах Vivo есть патчи на уровне ядра, блокирующие бинарник `su`, поэтому для использования Magisk следует прошить эту модифицированную версию с `suu`. Это касается только устройств с Funtouch; на устройствах с OriginOS (в основном это устройства для китайского рынка), хоть загрузчик всё ещё не разблокируем, `su` не блокируется.
- [Magisk][patched-magisk]
- [Magisk Delta][patched-magisk-delta]

\* Компания BBK Electronics была исключена из реестра компаний 7 апреля 2023 года.

***
Автор: [zenfyr](https://zenfyr.dev).

[BBK Fastboot]:https://xdaforums.com/t/how-to-unlock-bootloader-of-vivo-phones.3686690/
[Vivo x70 Pro+]:https://xdaforums.com/t/vivo-x70-pro-bootloader-unlock-how-to-guide.4444989/
[Vivo Y31 2021]:https://xdaforums.com/t/unlocking-bootloader-rebooting-in-edl-without-testpoint-vivo-y31-2021.4440801/
[patched-magisk]:https://github.com/4accccc/vivo-Magisk-suu/
[patched-magisk-delta]:https://github.com/4accccc/vivo-Magisk-Delta-suu