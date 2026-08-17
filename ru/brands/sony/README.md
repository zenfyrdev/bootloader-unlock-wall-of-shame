# Sony

- Вердикт: **⚠️ Действуйте осторожно!** (международные Xperia)

- Вердикт: **🍅 Ужасно!** (японские Xperia, устройства не Xperia)

У Sony открытая политика для разработчиков ПО:
- Они публикуют исходники AOSP в рамках [Sony Open Devices Program].
- Jolla обеспечивает первоклассную поддержку установки [Sailfish OS] на отдельные Xperia.

Поскольку Sony любит портить идеальную вещь:
- Для разблокировки Sony требует запросить код у их [Unlock Service]. Они могут свернуть этот сервис в любой момент. Вам нужно отправить свой IMEI и согласиться на возможную потерю гарантии (многие добивались ремонта или замены телефона по гарантии даже после разблокировки — просто прошейте сток и заблокируйте загрузчик перед обращением по гарантии).

Некоторые операторские заблокированные и американские устройства никогда не могут быть разблокированы. На устройствах Sony ([но не на всех?][service-menu-gone]) можно проверить, разблокируем ли загрузчик, через сервисное меню.

Кроме того, разблокируемы только Xperia (основная потребительская линейка телефонов/планшетов Sony). Их другие Android-устройства (такие как [телевизоры Bravia][Bravia unlock]) не разблокируются.

1. Наберите `*#*#7378423#*#*` в звонилке.
2. Нажмите "Service Info", затем "Configuration", затем "Rooting Status".
3. В Rooting Status найдите "Bootloader unlock allowed".
4. Если написано "Yes", значит устройство разблокируемо.

На устройствах, выпущенных [до 2019 года][TA patch 2019], есть раздел под названием `TA`, в котором хранятся файлы, необходимые для таких вещей, как улучшенная обработка изображений камеры, DRM-ключи и улучшения дисплея. При разблокировке загрузчика этот раздел стирается, и эти функции теряются даже при повторной блокировке. Если у вас Android Marshmallow или более ранняя версия, вы можете [сделать резервную копию][TA backup] раздела.

Sony поддерживает [Custom AVB](../../README.md#кастомные-avb-ключи) с 2020 года.

Также нельзя разблокировать японские операторские варианты, по какой-то причине — на разблокировку японских заводских разблокированных версий это не влияет.

Все устройства Sony на Snapdragon 835 и Snapdragon 845 можно разблокировать через [эксплойт xperable][xperable].

***
Информация о японских устройствах предоставлена [madeline-yana](https://github.com/madeline-yana) и отредактирована [eepymeowers](https://github.com/eepymeowers)
Дополнительная информация предоставлена [K4sum1](https://github.com/K4sum1).<br/>
Автор: [konradmb](https://github.com/konradmb).

[Sony Open Devices Program]:https://developer.sony.com/open-source/aosp-on-xperia-open-devices
[Sailfish OS]:https://shop.jolla.com/
[Unlock Service]:https://developer.sony.com/open-source/aosp-on-xperia-open-devices/get-started/unlock-bootloader
[service-menu-gone]:https://www.reddit.com/r/SonyXperia/comments/qir0ze/what_happened_to_the_service_menu/
[TA patch 2019]:https://www.reddit.com/r/SonyXperia/comments/1199y1j/what_are_the_consequences_of_getting_rid_off_the/
[TA backup]:https://together.jolla.com/question/168711/xperia-x-backup-ta-partition-before-unlocking-bootloader/
[Bravia unlock]:https://pro-bravia.sony.net/data/bz40h/ProBRAVIA_SecurityWhitePaper.pdf
[xperable]:https://github.com/j4nn/xperable