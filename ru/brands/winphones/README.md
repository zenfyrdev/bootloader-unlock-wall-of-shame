# Windows phones

- Вердикт: **🍅 Ужасно!**

Все Windows Phone объединены на одной странице, так как методы разблокировки у них очень похожи. Ни один из них официально не разрешал разблокировку загрузчика, но за годы были разработаны многочисленные методы от сообщества.

Перед разблокировкой отключите шифрование устройства!

## Большинство телефонов Nokia и Microsoft (см. исключения ниже)
> [!NOTE]
> Спецификация загрузчика A: Lumia 52x, 62x, 72x, 810, 82x, 92x, 1020, 1320.
> Спецификация загрузчика B: Lumia 43x, 53x (кроме 535), 540, 550, 63x, 640, 640 XL, 650, 73x, 830, 929 Icon, 930, 950, 950 XL, 1520.

Инструмент [WPInternals][wpinternals] позволяет разблокировать загрузчик двумя методами:

- Для спец. A: требуется стоковая прошивка, [HEX-загрузчики][hex-loaders], [инженерный SBL3][eng-sbl3] и [донорский FFU][donor-ffu].
- Для спец. B: требуется стоковая прошивка, [аварийные файлы][emergency-files] и [донорский FFU][donor-ffu]. **Требуется** USB 2.0 или старее.

## Lumia 535 и другие OEM на Windows 10 Mobile
Полной разблокировки нет, но возможен частичный доступ к ФС. Установите Interop Tools, получите доступ к реестру, измените ключ MTP на C:\EFIESP, затем переименуйте resetphone.efi в [developermenu.efi][devmenu]. При загрузке с Vol- появится меню разработчика с USB Mass Storage.

## Lumia 510, 610, 610C, 710, 800, 900
Некоторые Lumia 710/800/900 имеют загрузчик Qualcomm вместо Nokia — они разблокированы с завода. [Руководство по переключению загрузчика][lumia-wp7].

## HTC на Windows Phone 7.x
Можно разблокировать через HSPL/RSPL. [Первое поколение][first-gen-htc] и [второе поколение][second-gen-htc] (кроме Titan II). SPL 4.x и 5.x невозможно разблокировать — [руководство по откату][htc-downgrade-spl].

## Другие устройства
Все WP 8.x можно неофициально обновить до W10M. WP 7.x — нет.

[wpinternals]:https://github.com/ReneLergner/WPinternals
[eng-sbl3]:https://archive.org/download/sbl-3-no-buggy-62x/SBL3_NoBuggy62x.zip
[hex-loaders]:https://4pda.to/forum/dl/post/20979092/Hex_loader.zip
[donor-ffu]:https://download.lumiadb.com/RM-1085/RM1085_1078.0053.10586.13169.12742.034EE8_retail_prod_signed.ffu
[emergency-files]:http://protobetatest.com/download/lumia-emergency-files/
[interop-guide]:https://xdaforums.com/t/interop-tools-a-versatile-registry-app-for-all-devices-now-on-github.3445271/
[devmenu]:https://archive.org/download/w10m-9821-patchedfiles/developermenu.efi
[first-gen-htc]:https://xdaforums.com/t/dft-updated-3-hspl-rspl-for-htc-wp7-first-generation.1195647/
[second-gen-htc]:https://xdaforums.com/t/dft-hspl-for-htc-wp7-second-generation.1684912/
[htc-downgrade-spl]:https://xdaforums.com/t/noob-friendly-goldcard-spl-downgrade-method-no-android-phone-and-or-custom-wires.1597837/
[lumia-wp7]:https://xdaforums.com/t/tutorial-full-unlock-lumia-710-in-windows-using-nss-pro-detailed-updated.1721355/
[lumiawp7-blswitch]:https://xdaforums.com/t/how-to-bootloader-unlock-your-lumia-900-and-flash-a-custom-rom.2204994/post-39517020
