# TCL / BlackBerry

- Вердикт: **🍅 Ужасно!**

TCL начинала как контрактный производитель для BlackBerry. Контракт закончился в 2020 году, но TCL продолжила традицию BlackBerry — «безопасные загрузчики», то есть всё, чтобы сделать разблокировку невозможной. Маловероятно, что их загрузчики когда-либо станут разблокируемыми.

## Authboot
У TCL есть своя версия fastboot — `authboot`, которая **требует специальной авторизации от сервера для любых операций с загрузчиком**. Без неё невозможно разблокировать устройство или прошить неподписанные образы.

## Устройства BlackBerry до 2016
BlackBerry Priv и более старые модели производились не TCL, а оригинальной BlackBerry (Research in Motion/RIM) в Канаде. Даже у старых устройств BlackBerry нет эксплойта для разблокировки загрузчика. Устройства на BB10 имеют софтверный эксплойт для получения root через [модифицированный автозагрузчик][bb10 modded autoloaders]. По состоянию на 2026 год, единственные BlackBerry с эксплойтом — Passport и Priv (через прошивку загрузчика от прототипа, но [требуется выпайка eMMC][passport priv unlock]).

## Key2 series
BlackBerry KEY2 производились TCL с «безопасными» загрузчиками. Используется authboot, но в них не исправили Qualcomm-баг CVE-2021-1931, что привело к [полноценному инструменту разблокировки][kibo] без привязки.

> TCL выглядит премиум, но это всего лишь китайский подвал. Их «безопасность» только ограничивает пользователей, а телефоны не лучше и не безопаснее остальных.

***
Автор: [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>
Информация об authboot и инженерных моделях: [DiabloSat](https://github.com/progzone122)<br/>

[passport priv unlock]:https://balika011.hu/blackberry/guides/passport/conversion.php
[kibo]:https://github.com/BotchedRPR/kibo
[bb10 modded autoloaders]:https://bb10.root.sx/blog
[bb10 toolchain setup]:https://forum.waitberry.com/index.php/topic,12.0.html
