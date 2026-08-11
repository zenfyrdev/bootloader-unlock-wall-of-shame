# Apple

- Вердикт: **⛔ Избегать любой ценой!**

Как и ожидалось, Apple не разрешает разблокировку загрузчика и никогда не разрешала. Большинство устройств Apple также имеют агрессивную анти-откатную систему, не позволяющую откатиться до старой версии iOS для джейлбрейка.

## Подпись прошивок

У Apple есть сервер под названием «Tatsu Signing Server» (сокращённо TSS). Когда вы пытаетесь установить прошивку на устройство Apple, iTunes или Finder отправляют несколько вещей на TSS, чтобы он сгенерировал подписанный SHSH-блоб для разрешения восстановления:

- Model ID — идентификатор модели устройства (например, iPhone6,2 для iPhone 5s, iPad11,3 для iPad Air 3, iPhone10,3 для iPhone X).
- Build ID — идентификатор сборки iOS (iOS 14.3 — 18B92, iOS 10.3.3 — 14G60).
- ECID устройства — уникальная строка для каждого устройства, позволяющая SHSH-блоку работать только на вашем устройстве. Его нельзя подделать, так как ECID вшит в процессор при производстве.
- Тип восстановления: iTunes/Finder restore (с полной очисткой), iTunes/Finder update (обновление с компьютера) или OTA update (обновление на устройстве). Для каждого типа нужен свой SHSH-блоб.

TSS может дать один из трёх ответов:
- Ответ 1: Прошивка подписывается, SHSH-блоб может быть сгенерирован
- Ответ 2: Прошивка НЕ подписывается, SHSH-блоб НЕ может быть сгенерирован
- Ответ 3: Прошивка несовместима с устройством

Процесс создания блоба: у Apple есть закрытый ключ; bootROM на устройстве имеет открытый ключ для проверки. Когда получен ответ 1, TSS хеширует файл (SHA1 для устройств до 2016, SHA384 для 2016+). Устройство проверяет блоб открытым ключом, затем сверяет Model ID, build ID, ECID и тип восстановления.

Подпись прошивок была введена в 2009 году с iPhone 3GS. Устройства до этого (iPhone 2G, iPhone 3G, iPod Touch 1, «old bootrom» iPod Touch 2) не имеют подписи прошивок.

Обычно Apple прекращает подпись старых версий через 3-7 дней после выхода новой. Однако есть редкие случаи: iOS 6.1.3 всё ещё подписывается для iPhone 4S и старых iPad 2; iOS 8.4.1 — для iPhone 4S, iPhone 5, iPad 2/3/4, iPad mini 1, iPod Touch 5; iOS 10.3.3 — для iPhone 5s, iPad Air 1, iPad mini 2. [Legacy iOS Kit] может получить OTA-блоб и восстановиться с ним через checkm8.

### SEP

Начиная с Apple A7, Apple представила сопроцессор Secure Enclave Processor (SEP) для защиты данных, Touch ID и Face ID. Прошивка SEP часто обновляется и становится несовместимой со старыми версиями iOS. SEP есть на всех устройствах Apple с 2013 года (кроме iPhone 5c). Известно только два SEP-эксплойта: [blackbird] (A8-A10, 2014-2016) и [hardbird] (A7, 2013).

Для устройств на A9/A10 можно использовать [turdus merula] для отката — без привязки при наличии SHSH-блобов, иначе с привязкой.

## bootROM и iBoot эксплойты

bootROM — код на уровне SoC, первое, что выполняется при загрузке. Это read-only память. bootROM-эксплойт — аналог аппаратной разблокировки загрузчика. За последние десять лет найдено только два.

iBoot — загрузчик Apple. iBoot-эксплойт — аналог программной разблокировки, но iBoot обновляется с каждой версией iOS, и эксплойты быстро патчатся. Последняя версия iOS с известным iBoot-эксплойтом — 7.1.2 (2014).

### checkm8
[checkm8] (CVE-2019-8900) — bootROM-эксплойт, обнаруженный в 2019 году. Затрагивает все SoC Apple с A5 по A11 (устройства 2011-2017), а также iPad 6 (2018), iPad 7 (2019) и iPod Touch 7 (2019). Часть эксплойта затрагивает A12 и A13, но утечка памяти в DFU была пропатчена, что делает выполнение невозможным без нескольких месяцев в DFU.

Проблемы checkm8:
- Привязанный эксплойт — после перезагрузки нужно подключаться к компьютеру
- Нет поддержки Windows
- Крайне высокая частота сбоев на AMD CPU
- Для A5 нужен Arduino с USB Host Shield
- Для A7 на Linux почти всегда сбой

### usbliter8
[usbliter8] — bootROM-эксплойт, обнаруженный в 2026 году для Apple A12, A13, S5 и их вариантов. Требует микроконтроллер на RP2350 (например, Raspberry Pi Pico 2).

### Другие эксплойты
alloc8 (iPhone 3GS), limera1n (iPod touch 3, все A4), 24Kpwn (old bootrom iPod touch 2), Pwnage (iPhone 2G, iPod Touch 1, iPhone 3G). iBoot-эксплойты: DRA (32-bit iOS 7.0-7.1.2), HFS Heap Buffer Overflow (iOS 5.0-5.1.1), usb_control_msg(0x21, 2) (iOS 3.1-3.1.2), EVO (iOS 3.0).

***
Автор: [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>

[futurerestore]:https://github.com/futurerestore/futurerestore
[Legacy iOS Kit]:https://github.com/LukeZGD/Legacy-iOS-Kit
[turdus merula]:https://sep.lol/
[blackbird]:https://theapplewiki.com/wiki/Blackbird_Exploit
[hardbird]:https://theapplewiki.com/wiki/Hardbird_Exploit
[checkm8]:https://theapplewiki.com/wiki/Checkm8_Exploit
[Project Sandcastle]:https://projectsandcastle.org/
[usbliter8]:https://theapplewiki.com/wiki/Usbliter8_Exploit
