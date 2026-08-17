# Xiaomi/Redmi/POCO

- Вердикт: **🍅 Просто ужасно!**
- Вердикт: **⛔ Избегать любой ценой!** (Unisoc)

В прошлом Xiaomi позволяла разблокировать большинство своих устройств по истечении периода в 7+ дней (в зависимости от того, насколько новое устройство).

С запуском нового Android-форка Xiaomi, HyperOS, они внесли ряд изменений в процесс разблокировки, включая новые лимиты на устройства и требования к Mi Account.

Устройства на Unisoc никогда не будут разблокируемы — это *не* вина Xiaomi, Unisoc не допускает разблокировки.

## Android One

* [**🔓️ Руководство по разблокировке**](../../../misc/generic-unlock.md)

Устройства, выпускаемые с Android One, НЕ имеют каких-либо требований к разблокировке, перечисленных ниже. Они следуют стандартному процессу разблокировки Android.

## Требования к разблокировке устройства

Устройства, выпускаемые с MIUI или HyperOS, требуют активации вашего телефона на серверах Xiaomi перед разрешением разблокировки. Вы можете разблокировать только один телефон за 30 дней и четыре телефона в год.

После включения «Параметров разработчика» перейдите в «Настройки» > «Расширенные настройки» > «Параметры разработчика», включите OEM Unlock и откройте страницу «Статус разблокировки устройства». Если там указано «Заблокировано», вы можете продолжить, нажав кнопку «Добавить аккаунт и устройство», чтобы начать процесс.

Выполнение этих действий не разблокирует ваше устройство немедленно, но в конечном итоге даст вам разрешение на разблокировку. Таким образом, чтобы получить право на разблокировку, вас попросят выполнить эти шаги.

Xiaomi сообщит вам, что требуется прямо сейчас, когда вы нажмёте «Добавить аккаунт и устройство», но чтобы объяснить всё по порядку, она просит выполнить следующее:

* Ваше устройство должно быть привязано к аккаунту Xiaomi в хорошем состоянии (ещё лучше, если это не недавно созданный аккаунт)
* Вставленная SIM-карта с активным тарифным планом (если у устройства есть слот для SIM-карты)
* Wi-Fi отключён, а мобильные данные включены (если у устройства есть слот для SIM-карты)
* Если используется HyperOS:
    * Смотрите [новые требования HyperOS](#особенности-hyperos) ниже

Когда вы выполните все вышеперечисленные шаги, нажатие кнопки «Добавить аккаунт и устройство» должно показать сообщение «Успешно добавлено».

Чтобы фактически *выполнить* разблокировку, вам нужно будет использовать инструмент [Mi Unlock][miunlock] для Windows и следовать подсказкам, чтобы войти в режим fastboot и подключить устройство. Если вы не можете или не хотите использовать официальный инструмент, вы также можете использовать альтернативные инструменты, такие как [MiUnlockTool][py-miunlock] от [offici5l][offici5l], написанный на Python.

Уникальный ключ для разблокировки загрузчика вашего устройства получается с серверов Xiaomi, но существует обратный отсчёт на стороне сервера (поэтому ни один инструмент не может обойти серверное время), который начнётся только после выполнения всех вышеуказанных шагов. В большинстве случаев отсчёт составляет 3 дня (= 72 часа) для HyperOS и 7 дней (= 168 часов) для MIUI, но есть сообщения о том, что людей заставляли ждать ещё дольше, например, 14 или 30 дней.

Вы можете продолжать использовать своё устройство как обычно и в любое время проверять инструмент разблокировки, чтобы узнать, сколько времени осталось. Тем временем НЕ удаляйте свой аккаунт Xiaomi и не сбрасывайте телефон к заводским настройкам — эти действия могут привести к сбросу отсчёта к исходному значению.

> [!NOTE]
> Для устройств на MIUI (не HyperOS) некоторые каналы на [Bilibili][bilibili-shutdown] утверждают, что сервер проверки Xiaomi был отключён.

## Особенности HyperOS

В настоящее время **невозможно** официально разблокировать телефоны Xiaomi из региона Китая, особенно если устройство было импортировано, а вы находитесь за пределами Китая. Они удалили функцию разблокировки из своего приложения сообщества.

С HyperOS Xiaomi ввела дополнительный шаг в процесс разблокировки. Запрос на разблокировку устройства можно сделать внутри «Параметров разработчика», но только после того, как вы выполнили ещё один отдельный успешный запрос внутри [приложения Xiaomi Community][mi-community-app].

Для международной версии вы можете запросить разблокировку в их приложении Community в 00:00 по пекинскому (китайскому) времени [GMT+8][gmt+8].

[Требования для запроса в приложении Community][global-requirements] следующие:

* Ваш Mi Account активен более 30 дней.
* Версия приложения Xiaomi Community 5.3.31 или выше.
* [С 1 января 2025 года][updated-policies] Xiaomi позволяет разблокировать только 1 устройство в год. Это требование также было распространено на MIUI 14.
* Убедитесь, что в приложении Xiaomi Community выбран регион «Global», чтобы увидеть раздел «Разблокировка загрузчика» на вкладке «Мне».

Кроме того, [на форумах XDA][community-app-cap] люди обнаружили, что существует ограничение на количество людей (по оценкам, около 50 человек), которые могут отправлять запросы в день внутри приложения Community, и оно заполняется практически мгновенно, так что ваш единственный шанс успешно отправить запрос — это если вам повезёт со спамом запроса в полночь по пекинскому времени ([GMT+8][gmt+8]).

Существует скрипт [AQLR][aqlr] (сокращение от «application quota limit reached» — достигнут лимит квоты приложения) для автоматизации этого: он отправляет запрос Xiaomi непосредственно перед наступлением нового дня в Китае, и вы можете оставить свой компьютер работать с этим скриптом 24/7.

> [!WARNING]
> Даже если кажется, что вы не успели попасть в сегодняшнюю квоту, Xiaomi может сообщить «application quota limit reached» [по ошибке, даже если вы на самом деле попали в квоту][quota-error-problem]. Так что единственный способ убедиться в этом — нажать «Добавить аккаунт и устройство» на странице «Статус разблокировки устройства» в настройках.

## Обходные пути и эксплойты

### Snapdragon 8 Elite/8Gen3/8Gen2/8Gen1

Все эти методы объединяют обход QCOM SELinux и уязвимости повышения привилегий в службе Xiaomi MQSAS.

- Серия Xiaomi 17, POCO F8 Ultra, Redmi K90 Pro Max с Security Patch до февраля 2026 года, [смотрите здесь][xda-qcom-1]
- Серии Xiaomi 13, 14, 15, MIX Flip 2, Pad 8 Pro, Pad 6S Pro, Redmi K90/K80/K70/K60 Pro с Security Patch до января 2026 года, [смотрите здесь][xda-qcom-2]

Теоретически возможно откатить прошивку и разблокировать устройства **не на UFS от Kioxia**, [используя EDL-программатор и инженерный ABL][firehose].

### MSM89xx

[EDLUnlock][edl-unlock] — инструмент разблокировки на основе EDL для Xiaomi Mi A1 и, возможно, всех MSM89xx, произведённых до 2018 года.

### Другое

* **MlgmXyysd** — MlgmXyysd, разработчик оригинального скрипта обхода загрузчика, обнаружил новую уязвимость в устройствах Qualcomm, которая позволяет разблокировать загрузчик на большинстве телефонов с HyperOS 2 и 3. По некоторым источникам, вы можете связаться с ней на CoolAPK.
* ~~Некоторые пользователи утверждают, что посещение магазина Xiaomi и просьба к техническому специалисту откатить версию системы приводит к временному разблокированному состоянию. Некоторые сообщали о прошивке собственной системы в ходе этого процесса.~~
* ~~[HyperSploit][hypersploit] — более новый вариант. Это простая в использовании программа без внешних зависимостей.~~ Подтверждено, что устранено по состоянию на HyperOS версии 2.0.203.0. По-прежнему работает на старых версиях.
* ~~[Xiaomi-HyperOS-BootLoader-Bypass][xiaomi-hyperos-bootLoader-bypass] — оригинальное доказательство концепции, но оно написано на PHP и его утомительно настраивать.~~ То же, что и выше.

## Дополнительное чтение

- [Вопросы опросника Xiaomi BootLoader][bootloader-questionnaire] – собранные сообществом заметки и детали экзамена.
- [Awesome Xiaomi Bootloader Unlock][awesome-bootloader-unlock]
- [Некоторые исследования загрузчика, используемого в телефонах Xiaomi][xiaomi-bootloader]

И «обоснование» Xiaomi, [почему они это делают][official-guide]:

> **Разве блокировка загрузчика не противоречит «гиковскому» духу Xiaomi?**
>
> Блокировка загрузчика направлена на обеспечение лучшего пользовательского опыта, к чему мы стремились всё это время. В то же время мы предоставили инструмент разблокировки для продвинутых пользователей, которые знают, как прошивать и модифицировать свои устройства.
>
> Процедура разблокировки потребует доступа в интернет для получения пароля разблокировки. Кроме того, аккаунт Xiaomi, выполнивший вход на телефоне Xiaomi, и инструмент разблокировки должны совпадать. В противном случае запрос на разблокировку будет отклонён. Это гарантирует, что злоумышленники не получат доступ к вашим личным данным.

***
Обновлённая информация предоставлена [n1ses](https://github.com/n1ses) & [Crimson Fork/🌌🏳️‍⚧️&ΘΔ](https://cf.spaceport.nexus)  & [Mluo2011](https://github.com/Mluo2011) & [ysfchn](https://ysfchn.com) <br/>
Автор: [zenfyr](https://zenfyr.dev).

[official-guide]: https://new.c.mi.com/global/post/101245
[hypersploit]: https://github.com/TheAirBlow/HyperSploit
[xiaomi-hyperos-bootLoader-bypass]: https://github.com/MlgmXyysd/Xiaomi-HyperOS-BootLoader-Bypass
[bootloader-unlock-block-mainland-china]: https://xiaomitime.com/bootloader-unlocking-comes-to-an-end-with-xiaomi-hyperos-2-0-12926
[bootloader-unlock-block-mainland-china-alt]: https://xiaomi.eu/community/threads/right-now-is-there-any-way-to-unlock-the-bootloader-on-chinese-versions-of-xiaomi-devices.73029/#post-726609
[bootloader-unlock-block-global]: https://x.com/chunvn8888/status/1841901853073953254
[global-requirements]: https://new.c.mi.com/global/post/673501
[xiaomi-bootloader]: https://github.com/lrh2000/Xiaomi-bootloader
[yo-dawg-meme]: https://i.kym-cdn.com/photos/images/small/000/001/122/xzibit-happy.jpg "I heard you liked unlock requests…"
[community-app-cap]: https://xdaforums.com/t/application-quota-limit-reached.4695764
[updated-policies]: https://xiaomitime.com/xiaomi-global-bootloader-unlock-policy-has-changed-20295
[other-requirements]: https://xiaomitime.com/xiaomi-restricts-bootloader-unlocking-with-new-180-day-rule-23160
[aqlr]: https://xdaforums.com/t/how-to-unlock-bootloader-on-xiaomi-hyperos-all-devices-except-cn.4654009/post-89311595
[mi-community-app]: https://play.google.com/store/apps/details?id=com.mi.global.bbs
[quota-error-problem]: https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame/issues/287
[xda-qcom-1]: https://xdaforums.com/t/xiaomi17-series-and-pocof8ultra-redmi-k90-pro-max-unlock-bootloader-xiaomi8elite5seriesbootloader-unlock.4781439/
[xda-qcom-2]: https://xdaforums.com/t/guide-breakthrough-free-offline-bootloader-unlock-for-cn-xiaomi15-pro-ultra-redmi-k90-sd-8-elite-also-support-8g2-8g3-no-cn-exam-required.4786790/
[gmt+8]:https://time.is/GMT%208
[offici5l]:https://offici5l.github.io
[py-miunlock]:https://github.com/offici5l/MiUnlockTool
[miunlock]:https://en.miui.com/unlock/download_en.html
[bilibili-shutdown]: https://www.bilibili.com/video/BV15Ut2z5Epo/?spm_id_from=333.1387.search.video_card.click&vd_source=96eca9b96bc62dc161f76ff2ff1fc1f3
[firehose]: https://xdaforums.com/t/unlock-bootloader-unbrick-xiaomi-8-elite-high-versions-auth-free-edl-firehose.4787466/
[edl-unlock]: https://github.com/Giovix92/EDLUnlock
[bootloader-questionnaire]: https://github.com/MlgmXyysd/Xiaomi-BootLoader-Questionnaire
[awesome-bootloader-unlock]: https://github.com/topminipie/awesome-xiaomi-bootloader-unlock