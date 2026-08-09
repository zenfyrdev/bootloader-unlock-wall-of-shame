# Fairphone

- Вердикт: **⚠️ Действуйте осторожно!**

Начиная с прошивки [FP3.6.A.040.2] на Fairphone 3, прошивки [FP4.QREL.15.17.2] на Fairphone 4, прошивки [FP5.VT2X.C.107] на Fairphone 5 и прошивки [FP6.QREL.16.69.0] на Fairphone (Gen. 6), Fairphone перешёл на [стандартную процедуру разблокировки](../../misc/generic-unlock.md). Опция OEM unlock по-прежнему требует подключения к интернету для проверки запроса.

Все Fairphone после второй модели требуют запросить код с [этого][unlock-website] сайта, чтобы включить OEM unlock. Ничто не мешает им в будущем ввести обязательную учётную запись и ограничения на разблокировку устройств. В конце концов, это «действуйте осторожно».

На мой взгляд, это не очень fair, но как говорится, каждому своё.

Существует [обходной путь][workaround], позволяющий обойти официальный сервер с помощью mitmproxy для авторизации разблокировки, поскольку криптографической подписи нет — только HTTP-код состояния.

Ещё они [сломали Verified Boot][verified-boot], лол

***
Автор: [zenfyr](https://zenfyr.dev).

[FP3.6.A.040.2]:https://forum.fairphone.com/t/software-update-fp3-6-a-040-2/130354
[FP4.QREL.15.17.2]:https://forum.fairphone.com/t/software-update-fp4-qrel-15-17-2-20260415141502/132010
[FP5.VT2X.C.107]:https://forum.fairphone.com/t/software-update-fp5-vt2x-c-107-20260609/132531
[FP6.QREL.16.69.0]:https://forum.fairphone.com/t/software-update-fp6-qrel-16-69-0-20260430160633/131953
[unlock-website]:https://shop.fairphone.com/bootloader-unlocking-code-for-fairphone
[verified-boot]:https://forum.fairphone.com/t/bootloader-avb-keys-used-in-roms-for-fairphone-3-4/83448/4
[workaround]:https://www.datenrei.ch/blog/2024/05/25/fp-oem-unlock-all.html