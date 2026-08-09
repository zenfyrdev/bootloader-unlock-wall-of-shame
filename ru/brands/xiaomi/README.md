# Xiaomi/Redmi/POCO

- Вердикт: **🍅 Просто ужасно!**
- Вердикт: **⛔ Избегать любой ценой!** (Unisoc)

В прошлом Xiaomi позволяла разблокировать большинство своих устройств по истечении периода в 7+ дней (в зависимости от того, насколько новое устройство).

С запуском нового Android-форка Xiaomi, HyperOS, они внесли ряд изменений в процесс разблокировки, включая новые лимиты на устройства и требования к Mi Account.

Устройства на Unisoc никогда не будут разблокируемы — это *не* вина Xiaomi, Unisoc не допускает разблокировки. 

## HyperOS

В настоящее время **невозможно** официально разблокировать телефоны Xiaomi из региона Китая, особенно если устройство было импортировано, а вы находитесь за пределами Китая. Они удалили функцию разблокировки из своего приложения сообщества.

С HyperOS Xiaomi ввела дополнительный шаг в процесс разблокировки. Запрос на разблокировку устройства можно сделать внутри «Параметров разработчика», но только после того, как вы выполнили ещё один отдельный успешный запрос внутри приложения Xiaomi Community.

Для международной версии вы можете запросить разблокировку в их приложении Community в 00:00 по китайскому времени GMT+8.

Если верить [xiaomiui.net][global-requirements], требования для запроса в приложении Community следующие:
* Ваш Mi Account активен более 30 дней.
* Версия приложения Xiaomi Community 5.3.31 или выше.
* [С 1 января 2025 года][updated-policies] Xiaomi позволяет разблокировать только 1 устройство в год. Это требование также было распространено на MIUI 14.

Кроме того, [на форумах xda][community-app-cap] люди обнаружили, что существует ограничение на количество людей (по оценкам, около 50 человек), которые могут отправлять запросы в день внутри приложения Community, и оно заполняется практически мгновенно, так что ваш единственный шанс успешно отправить запрос — это если вам повезёт со спамом запроса в полночь по пекинскому времени ([GMT+8][gmt+8]).

### Обходные пути

#### Snapdragon 8 Elite/8Gen3/8Gen2/8Gen1

Все эти методы объединяют обход QCOM SELinux и уязвимости повышения привилегий в службе Xiaomi MQSAS.

- Серия Xiaomi 17, POCO F8 Ultra, Redmi K90 Pro Max с Security Patch до февраля 2026 года: [XDA](https://xdaforums.com/t/xiaomi17-series-and-pocof8ultra-redmi-k90-pro-max-unlock-bootloader-xiaomi8elite5seriesbootloader-unlock.4781439/)
- Серии Xiaomi 13, 14, 15, MIX Flip 2, Pad 8 Pro, Pad 6S Pro, Redmi K90/K80/K70/K60 Pro с Security Patch до января 2026 года: [XDA](https://xdaforums.com/t/guide-breakthrough-free-offline-bootloader-unlock-for-cn-xiaomi15-pro-ultra-redmi-k90-sd-8-elite-also-support-8g2-8g3-no-cn-exam-required.4786790/)

Теоретически возможно откатить прошивку и разблокировать устройства **не на UFS от Kioxia**, используя EDL-программатор и инженерный ABL: [XDA](https://xdaforums.com/t/unlock-bootloader-unbrick-xiaomi-8-elite-high-versions-auth-free-edl-firehose.4787466/)

### Другое

* [AQLR][aqlr] — текущий метод обхода, однако вам нужно, чтобы ваш компьютер работал в 00:00 по китайскому времени ([GMT+8][gmt+8]). (Скрипт находится в AQLR.zip в конце поста.)
* **MlgmXyysd** — MlgmXyysd, разработчик оригинального скрипта обхода загрузчика, обнаружил новую уязвимость в устройствах Qualcomm, которая позволяет разблокировать загрузчик на большинстве телефонов с HyperOS 2 и 3. По некоторым источникам, вы можете связаться с ней на CoolAPK.
* ~~Некоторые пользователи утверждают, что посещение магазина Xiaomi и просьба к техническому специалисту откатить версию системы приводит к временному разблокированному состоянию. Некоторые сообщали о прошивке собственной системы в ходе этого процесса.~~ 
* ~~[HyperSploit][hypersploit] — более новый вариант. Это простая в использовании программа без внешних зависимостей.~~ Подтверждено, что устранено по состоянию на HyperOS версии 2.0.203.0. По-прежнему работает на старых версиях.
* ~~[Xiaomi-HyperOS-BootLoader-Bypass][xiaomi-hyperos-bootLoader-bypass] — оригинальное доказательство концепции, но оно написано на PHP и его утомительно настраивать.~~ То же, что и выше.

В самом конце процесса разблокировки можно использовать Python-инструмент [MiUnlockTool][py-MiUnlockTool] от [offici5l][offici5l] вместо официального [Mi Unlock][MiUnlock] только для Windows.

### Дополнительное чтение

- [Вопросы опросника Xiaomi BootLoader](https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire) – собранные сообществом заметки и детали экзамена. 

## MIUI 14 и ниже

> [!NOTE]
>На [Bilibili](https://www.bilibili.com/video/BV15Ut2z5Epo/?spm_id_from=333.1387.search.video_card.click&vd_source=96eca9b96bc62dc161f76ff2ff1fc1f3) некоторые каналы утверждают, что сервер проверки Xiaomi был отключён.

Вы должны иметь возможность использовать «обычный» процесс разблокировки без приложения Community.

* Убедитесь, что в приложении «Настройки» на устройстве выполнен вход в аккаунт Xiaomi
* Перейдите в «Параметры разработчика» > «Статус Mi Unlock» и нажмите кнопку, чтобы запросить разблокировку вашего устройства на серверах Xiaomi
* Затем по истечении 7+ дней вы можете использовать официальный [Mi Unlock][MiUnlock] для Windows или Python [MiUnlockTool][py-MiUnlockTool] от [offici5l][offici5l], который проверит эти серверы, чтобы узнать, был ли отправлен запрос для этого конкретного устройства, и позволит вам разблокировать его.

### Обходные пути

Инструмент разблокировки на основе EDL для Xiaomi Mi A1 и, возможно, всех MSM89**, произведённых до 2018 года:<br/>
[EDLUnlock](https://github.com/Giovix92/EDLUnlock)

### Дополнительное чтение

Загляните сюда, если хотите узнать о том, как раньше работал загрузчик Xiaomi: [Xiaomi-bootloader] <br/>
Альтернативные инструменты вместо Mi Flash Unlock: [Awesome Xiaomi BootLoader Unlock](https://github.com/topminipie/awesome-xiaomi-bootloader-unlock)


## Android One

* [**🔓️ Руководство по разблокировке**](../../misc/generic-unlock.md)

Устройства, выпускаемые с Android One, НЕ имеют никаких требований к разблокировке. Они следуют стандартному процессу разблокировки Android.

***
Обновлённая информация предоставлена [n1ses](https://github.com/n1ses) & [Crimson Fork/🌌🏳️‍⚧️&ΘΔ](https://cf.spaceport.nexus)  & [Mluo2011](https://github.com/Mluo2011) <br/>
Автор: [zenfyr](https://zenfyr.dev).

[hypersploit]:https://github.com/TheAirBlow/HyperSploit
[xiaomi-hyperos-bootLoader-bypass]:https://github.com/MlgmXyysd/Xiaomi-HyperOS-BootLoader-Bypass
[bootloader-unlock-block-mainland-china]:https://xiaomitime.com/bootloader-unlocking-comes-to-an-end-with-xiaomi-hyperos-2-0-12926
[bootloader-unlock-block-mainland-china-alt]:https://xiaomi.eu/community/threads/right-now-is-there-any-way-to-unlock-the-bootloader-on-chinese-versions-of-xiaomi-devices.73029/#post-726609
[bootloader-unlock-block-global]:https://x.com/chunvn8888/status/1841901853073953254
[global-requirements]:https://xiaomiui.net/how-unlock-bootloader-xiaomi-hyperos-53493
[Xiaomi-bootloader]:https://github.com/lrh2000/Xiaomi-bootloader
[yo-dawg-meme]:https://i.kym-cdn.com/photos/images/small/000/001/122/xzibit-happy.jpg "I heard you liked unlock requests…"
[community-app-cap]:https://xdaforums.com/t/application-quota-limit-reached.4695764
[updated-policies]:https://xiaomitime.com/xiaomi-global-bootloader-unlock-policy-has-changed-20295
[other requirements]:https://xiaomitime.com/xiaomi-restricts-bootloader-unlocking-with-new-180-day-rule-23160
[aqlr]:https://xdaforums.com/t/how-to-unlock-bootloader-on-xiaomi-hyperos-all-devices-except-cn.4654009/post-89311595
[gmt+8]:https://time.is/GMT%208
[offici5l]:https://offici5l.github.io
[py-MiUnlockTool]:https://github.com/offici5l/MiUnlockTool
[MiUnlock]:https://en.miui.com/unlock/download_en.html