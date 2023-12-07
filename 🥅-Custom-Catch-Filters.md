# Filename
`customcatchfilters.py`

# Information
All Pokémon encounters are checked by custom catch filters, use this file if you are after Pokémon that match very specific criteria, some examples are provided (most are disabled by default).

These filters are checked *after* the catch block list, so if Wurmple is on your [catch block list](https://github.com/40Cakes/pokebot-gen3/wiki/%E2%9D%8C-Catch-Block-List), the Wurmple evolution example below will still be checked.

If you are not familiar with Python, it is highly recommended to use an IDE such as [PyCharm](https://www.jetbrains.com/pycharm/) to edit this file as any syntax errors will be highlighted, and the `pokemon` object will auto-complete and show available parameters for you to filter on.

- `return "any message"` (string) - will command the bot to catch the current encounter, the string returned will be added to the Discord webhook if `custom_filter_pokemon_encounter` is enabled in [Discord config](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%93%A2-Discord-Integration)
- `pass` - will skip the check, and continue to check other criteria further down the file
- `save_pk3(pokemon)` instead of `return "any message"` will [dump a .pk3 file](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%93%84-Logging-and-Console-Output) and continue without pausing the bot until auto-catch is ready

The following example will catch any shiny Wurmple that will evolve into Silcoon/Beautifly, and ignore any that would evolve into Cascoon/Dustox:

```py
# Shiny Wurmple evolving based on evolution
if pokemon.is_shiny and pokemon.species.name == "Wurmple":
    if pokemon.wurmple_evolution == "silcoon":
        return "Shiny Wurmple evolving into Silcoon/Beautifly"
    if pokemon.wurmple_evolution == "cascoon":
        pass
```

The following example will catch any Pokémon with all perfect IVs:
```py
# Pokémon with perfect IVs
if pokemon.ivs.sum() == (6 * 31):
    return "Pokémon with perfect IVs"
```

- **Note**: you must restart the bot after editing this file for changes to take effect!