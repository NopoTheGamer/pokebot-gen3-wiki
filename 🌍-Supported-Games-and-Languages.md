Variations of games, languages and revisions may have different memory offsets, there will be a table of supported/tested variations under each bot mode listed on this wiki.

- ✅ Supported (tested)
- 🟨 Supported (not tested)
- ❌ Not supported

It is highly recommended to use English ROMs for now as English is typically prioritised during development, however the goal is to eventually support all languages, please be patient if you find your language is not supported.

ROM hacks will likely not work, and are ❌ **not supported** or planned to be supported!

The ROMs in the `roms/` folder are checked and verified against a list of all known official gen3 game hashes. If you **really** want to test a ROM hack with the bot, you must add the SHA1 hash of the ROM to [`modules/roms.py`](https://github.com/40Cakes/pokebot-gen3/blob/main/modules/roms.py).

The SHA1 hash of a ROM can be calculated with any of the following methods:
- [ROM Hasher](https://www.romhacking.net/utilities/1002/)
- Windows Powershell: `Get-FileHash 'rom_name.gba' -Algorithm SHA1`
- Linux: `sha1sum 'rom_name.gba'`

Please do not seek support or complain if you find that your ROM hack does not work with the bot.