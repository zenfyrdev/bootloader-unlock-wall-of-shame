# LG

- Вердикт: **⛔ Избегать!**
- Вердикт: **🍅 Ужасно!** (Unisoc)
- Вердикт (часы): **ℹ️ «Пока безопасно» :trollface:**

Раньше у LG был портал для разработчиков, где можно было разблокировать телефоны, но он поддерживал только международные модели. В декабре 2021 LG [объявила][announcement-archive] о закрытии портала из-за прекращения производства телефонов. Устройства на Unisoc никогда не будут разблокируемы — это *не* вина LG.

На некоторых моделях (Stylo 3 Plus, G6) загрузчик можно разблокировать через `fastboot oem unlock`, **только если [телефон от T-Mobile][t-mobile-unlock]**.

Старые устройства (до 2015) не имеют проверки разделов — при наличии root-доступа можно просто прошить модифицированные разделы через dd.

## Часы
Все часы LG на Android Wear/Wear OS используют [стандартную процедуру разблокировки](../../misc/generic-unlock.md) через fastboot.

***
Автор: [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439), [DiabloSat](https://github.com/progzone122)<br/>

[announcement-archive]:https://www.reddit.com/r/LineageOS/comments/r961u3/termination_of_lg_mobile_developer_website/
[t-mobile-unlock]:https://xdaforums.com/t/unlock-bootloader-tmo.3578099/
[install guides]:https://wiki.lineageos.org/devices/d852/install/#installing-a-custom-recovery-using-dd
