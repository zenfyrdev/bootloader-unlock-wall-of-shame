# HTC

- Вердикт: **⛔ Избегать!**
- Вердикт: **🍅 Ужасно!** (Unisoc/Spreadtrum)

Раньше HTC позволяла разблокировать загрузчик на [своём сайте для разработчиков][developer website], но в июне 2018 года HTC объявила, что новые телефоны не будут иметь разблокируемых загрузчиков. За несколько месяцев до этого HTC продала всё своё телефонное подразделение Google. Unisoc и Spreadtrum устройства никогда не будут разблокируемы — это *не* вина HTC.

> [!NOTE]
> По состоянию на сентябрь 2024 года сайт всё ещё работает (проверено на HTC Raider), но поскольку HTC не поддерживала его более 6 лет, он может упасть в любой момент.

## S-ON/S-OFF

У HTC была система S-ON/S-OFF. С S-ON [единственные разделы, которые можно прошить — system и recovery][s-system], все остальные разделы только для чтения.

Хотя HTC утверждает, что можно записать boot при S-ON, это сложно. HTC сделала так, что нельзя прошить boot.img из recovery — нужно прошивать его в fastboot. Есть обходные пути, такие как [HTC Dumlock] от TWRP. Способы достижения S-OFF отличаются для каждого устройства. Из-за возраста большинства инструментов могут потребоваться устаревшие ОС, такие как **Ubuntu 14.04 или Windows 7**.

***
Автор: [Ivy / Lost-Entrepreneur439](https://github.com/Lost-Entrepreneur439).<br/>

[developer website]:https://www.htcdev.com/bootloader
[s-system]:https://www.htcdev.com/bootloader/about_unlock_process
[HTC Dumlock]:https://xdaforums.com/t/htc-dumlock-flash-boot-from-recovery-without-fastboot-updated-2012-02-28-v2.1509743/
