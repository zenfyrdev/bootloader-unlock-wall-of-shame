# Gigaset

- Verdict: **⚠️ Proceed with caution!**

Depending on the SoC your Phone uses your experience may vary. Gigaset is known to use 3 different SoCs:

## Unisoc
devices such as the GP20 cannot be easily unlocked. While you can allow unlocking in the Developer options you cannot unlock the Phone in fastboot by any known method some of those below may work for Unisoc
### Unofficial Unlock

- [💡 Universal SOC-based methods](../../README.md#universal-soc-based-methods)
- another option could be a BROM exploit however Gigaset does not provide any Stock-ROM files and you can't really find 3rd parties hosting them - so even if you succeed and flash a custom rom or similar you will not be able to restore the device to stock if you didn't backup your ``.pac`` file
- maybe there is a specific exploit for your phone and android version (if you did not update for a long time) - but no general advice can be given aside from: [VoLTE Exploit](https://thehackernews.com/2026/08/unisoc-volte-video-call-exploit-chain.html)

## MediaTek

*Not owning the device therefore no info - contributions welcome.*

## Qualcomm

*Not owning the device therefore no specific info* however:
- Older Qualcomm models (e.g. the GS185, Snapdragon 425) unlock normally: enable *OEM unlocking* in Developer options, then `fastboot flashing unlock`.

---

Authored by [DanLP6](https://github.com/schooldanlp6).
