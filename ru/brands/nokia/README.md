# HMD Global/Nokia

- Вердикт: **🍅 Просто ужасно!**

## HMD

Официально невозможно разблокировать большинство телефонов HMD/Nokia. Однако, по словам Hikari Calyx, серия HMD Fusion [разблокируема][fusion-unlock]. Неизвестно, является ли это просто ошибкой HMD или HMD планирует ввести разблокировку загрузчика.

Некоторые ранние устройства Nokia времен HMD можно разблокировать, получив md5-хэш серийного номера, выполнив `fastboot oem key YOUR_MD5_SUM` в режиме Fastboot, а затем `fastboot flashing unlock`.

### Неофициальная разблокировка

- [💡 Универсальные методы на базе SoC](../../README.md#universal-soc-based-methods)

#### Сервис Hikari Calyx

Модели, выпущенные до начала 2019 года, могут запросить разблокировку через неофициальный сервис Hikari Calyx [hikaricalyx.com][hikari-service]

#### Прототипные ABL

У Hikari Calyx есть репозиторий с прототипными ABL для некоторых других моделей. [fih-firmware.hikaricalyx.com][hikari-abl]

#### HMD Device Kit

Модели 7.2, 8.3 и 5.3 можно разблокировать офлайн, тогда как для остальных может понадобиться HMD Device Kit, **который не является публичным и требует сервисной учётной записи.**

***
Информация о Windows Phone от [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>
Обновлённая информация предоставлена [Hikari Calyx](https://github.com/HikariCalyx).<br/>
Автор: [zenfyr](https://zenfyr.dev).

[hikari-service]:https://hikaricalyx.com/request-bootloader-unlock
[hikari-abl]:https://fih-firmware.hikaricalyx.com/protoabl/
[fusion-unlock]:https://fixupx.com/Hikari_Calyx/status/1932739593385976145