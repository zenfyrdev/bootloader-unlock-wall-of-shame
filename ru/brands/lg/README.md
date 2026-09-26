# LG

- Вердикт: **🍅 Просто ужасно!**
- Вердикт: **⛔ Избегать любой ценой!** (Unisoc)
- Вердикт (часы): **ℹ️ «Пока безопасно» :trollface:**

Раньше у LG был портал для разработчиков, где можно было разблокировать телефоны, но он поддерживал только **некоторые** международные модели. В декабре 2021 LG [объявила][announcement-archive] о закрытии портала из-за прекращения производства телефонов. Устройства на Unisoc никогда официально не были разблокируемы — это *не* вина LG, Unisoc официально не поддерживает разблокировку.

На некоторых моделях (таких как Stylo 3 Plus и G6) загрузчик всё ещё можно официально разблокировать через `fastboot oem unlock`, **только если [телефон от T-Mobile][t-mobile-unlock]**. Версии T-Mobile также имеют удалённые большинство команд fastboot, включая `fastboot flash`, `erase` и `boot`, начиная с [LG V10 на Android 6][TMO Fastboot commands removed]. Кроме того, на некоторых [не-T-Mobile устройствах LG][Fastboot commands removed INT] [(пример 2)][USC Fastboot commands removed] также удалены `fastboot boot`, `flash` и/или `erase`.

Старые устройства (до 2015) не имеют проверки разделов (на версиях ОС, выпущенных до 2015) — при наличии root-эксплойта можно просто прошить модифицированные разделы через dd, как рекомендуется в некоторых официальных [инструкциях][install guides] LineageOS.

Новые бюджетные телефоны LG (2018+) серий K и Stylo обычно не имеют видимого Fastboot.

На большинстве устройств LG со скрытым fastboot к нему можно получить доступ, стерев LG Download mode (также известный как LAF). Обычно он стирается либо через root (устройства до 2015), либо через EDL (устройства с 2015).

Большинство устройств LG под оператора (кроме устройств T-Mobile, выпущенных до 2018) также обычно имеют скрытый Fastboot.

## Часы
Все часы LG на Android Wear/Wear OS используют [стандартную процедуру разблокировки](../../misc/generic-unlock.md) через fastboot.

## Неофициальные методы
Помимо общих неофициальных методов для устройств на MediaTek, Unisoc и Devinfo (для некоторых Qualcomm SoC), на некоторых устройствах с Qualcomm SoC доступны утёкшие [инженерные загрузчики][SDM845 ENG Boot], например для LG G7.

Также существуют эксплойты загрузчика, такие как [CVE-2020-12753] ([PoC]) ([Рабочий пример]) и [этот][V30 bootloader unlock exploit], которые позволяют разблокировать загрузчик.


***
Автор: [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439), [DiabloSat](https://github.com/progzone122), [TheEnby](https://github.com/TheEnby)<br/>

[announcement-archive]:https://www.reddit.com/r/LineageOS/comments/r961u3/termination_of_lg_mobile_developer_website/
[t-mobile-unlock]:https://xdaforums.com/t/unlock-bootloader-tmo.3578099/
[install guides]:https://wiki.lineageos.org/devices/d852/install/#installing-a-custom-recovery-using-dd

[CVE-2020-12753]:https://douevenknow.us/post/619763074822520832/an-el1el3-coldboot-vulnerability?

[PoC]:https://github.com/shinyquagsire23/CVE-2020-12753-PoC

[TMO Fastboot commands removed]:https://xdaforums.com/t/v10-bootloop-fix-lengthens-life.3694064/post-74461372

[USC Fastboot commands removed]:https://xdaforums.com/t/lg-v30-v30-v30s-bootloader-unlock-root-method-with-clear-instructions.3790500/post-76573357

[Fastboot commands removed INT]:https://xdaforums.com/t/recovery-official-f500-ls991-h81x-us991-vs986-a7-a9-twrp-2020-06-22.3442424/post-73830593

[Рабочий пример]:https://xdaforums.com/t/rle888-bootloader-unlock-exploit-for-the-lg-g5.4792237/

[V30 bootloader unlock exploit]:https://xdaforums.com/t/lg-v30-v30-v30s-bootloader-unlock-root-method-with-clear-instructions.3790500/

[SDM845 ENG Boot]:https://xdaforums.com/t/guide-guide-to-unlock-bootloader-for-every-lg-sdm845-except-g710tm-with-photos.4168771/
