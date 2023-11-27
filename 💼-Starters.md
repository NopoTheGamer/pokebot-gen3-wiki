Soft reset for starter Pokémon.

https://github.com/40Cakes/pokebot-gen3/assets/16377135/54f7f774-8cc1-4c6e-a6f7-b8474b66637b

- For modes that use soft resets such as starters, the bot will track RNG to ensure a unique frame is hit after every reset, this is to prevent repeatedly generating an identical Pokémon, this will cause soft resets to take progressively longer over time
- If resets begin to take too long, it is recommended to start a new save file with a different TID to reset this delay or check out [`profiles/cheats.yml`](#cheatsyml---cheats-config)
- **Note**: Even though you set the trainer to face the desired PokéBall, it is still important to set the correct `starter` in the config! This option is used by the bot to track frames to ensure a unique starter is generated every time
- **Note**: For the time being, Johto starters will automatically enable the `starters` option in [`profiles/cheats.yml`](#cheatsyml---cheats-config), the shininess of the starter is checked via memhacks as start menu navigation is WIP (in future, shininess will be checked via the party summary menu)

### FireRed and LeafGreen (Kanto)
1. Select the `starter` in `profiles/general.yml` - `Bulbasaur`, `Charmander` or `Squirtle`
2. Face the desired PokéBall in Oak's lab, save the game (**in-game, not a save state**)
3. Start the bot

### Emerald (Johto)
1. Select the `starter` in `profiles/general.yml` - `Chikorita`, `Cyndaquil` or `Totodile`
2. Face the desired PokéBall in Birch's lab, save the game (**in-game, not a save state**)
3. Start the bot

### Ruby, Sapphire and Emerald (Hoenn)
1. Select the `starter` in `profiles/general.yml` - `Treecko`, `Torchic` or `Mudkip`
2. Face the starters bag, and save the game (**in-game, not a save state**)
3. Start the bot

|          | 🟥 Ruby | 🔷 Sapphire | 🟢 Emerald | 🔥 FireRed | 🌿 LeafGreen |
|:---------|:-------:|:-----------:|:----------:|:----------:|:------------:|
| English  |    ✅    |      ✅      |     ✅      |     ✅      |      ✅       |
| Japanese |    ❌    |      ❌      |     ❌      |     ❌      |      ❌       |
| German   |    ❌    |      ❌      |     ❌      |     ❌      |      ❌       |
| Spanish  |    ❌    |      ❌      |     ❌      |     ❌      |      ❌       |
| French   |    ❌    |      ❌      |     ❌      |     ❌      |      ❌       |
| Italian  |    ❌    |      ❌      |     ❌      |     ❌      |      ❌       |

✅ Supported (tested)

🟨 Supported (not tested)

❌ Not supported