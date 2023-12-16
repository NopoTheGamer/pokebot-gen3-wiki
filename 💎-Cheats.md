Perform actions not possible by a human, such as peeking into eggs to check shininess, knowing instantly which route a roamer is on, instantly locate Feebas tiles etc.

RNG manipulation options may be added to the bot in the future, all cheats are disabled by default.

# Config Filename
[`cheats.yml`](https://github.com/40Cakes/pokebot-gen3/blob/main/profiles/cheats.yml)

# Information
`fast_check_starters` - soft reset as soon as possible after receiving the starter Pokémon, this will bypass slow battle/menu animations, saving a little bit of time

`random_soft_reset_rng` - inject a random value into `gRngValue` before while using soft-reset methods
- Removes all delays before selecting the Pokémon, preventing resets from progressively slowing down over time as the bot waits for unique frames
- Gen3 Pokémon games use predictable methods to seed RNG, this can cause the bot to find identical PID Pokémon repeatedly after every reset (which is why RNG manipulation is possible), see [here](https://blisy.net/g3/frlg-starter.html) and [here](https://www.smogon.com/forums/threads/rng-manipulation-in-firered-leafgreen-wild-pok%C3%A9mon-supported-in-rng-reporter-9-93.62357/) for more technical information
- Uses Python's built-in [`random`](https://docs.python.org/3/library/random.html) library to generate and inject a 'more random' (still pseudo-random) 32-bit integer into the `gRngValue` memory address, essentially re-seeding the game's RNG

`faster_pickup` - read memory directly instead of manually checking the party menu for pickup items, if pickup mode is enabled

# Defaults
```yml
fast_check_starters: false
random_soft_reset_rng: false
faster_pickup: false
```