The bot can automatically battle Pokémon that don't meet catch criteria.

# Config Filename
[`battle.yml`](https://github.com/40Cakes/pokebot-gen3/blob/main/profiles/battle.yml)

# Information
## Pickup
`pickup` - enable pickup farming, the bot will use [Pickup (ability)](https://bulbapedia.bulbagarden.net/wiki/Pickup_(Ability)) to items from Pokémon who have picked up items. See [Pickup items](https://bulbapedia.bulbagarden.net/wiki/Pickup_(Ability)#Items_received).

`pickup_threshold` - number of Pokémon in the party that should have an item before the bot tries to take items from them. If you have fewer Pokémon with Pickup in your party than this number, the bot will use that number instead.

`pickup_check_frequency` - wait interval encounters to get before checking for pickup items.
- If `faster_pickup` is enabled in [💎 Cheats](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%92%8E-Cheats), this threshold is ignored.

## Battling
`battle` - enable battling opponents

`battle_method` - placeholder for an intelligent battle engine in the future.

`faint_action` - how to behave if lead Pokémon faints. 
- `stop` - go into manual mode
- `flee` - run from the encounter
- `rotate` - send out the next Pokémon in the party (must have at least 20% of its health and at least 1 usable move)

`new_move` - how to behave if a Pokémon attempts to learn a new move.
- `stop` - go into manual mode
- `cancel` - stop the Pokémon from learning a new move
- `learn_best`- calculate the weakest move from the Pokémon's current move set. If the new move is better, replaces that move with the new move. If the Pokémon knows more than one move of a certain type, the bot will attempt to delete the weakest move with redundant typing in order to maximize coverage

`stop_evolution` - prevent Pokémon from evolving

`replace_lead_battler` - switch the order of Pokémon in the party to replace a lead Pokémon that runs out of PP or runs low on HP. Helpful for leveling the whole team.

`switch_strategy` - Placeholder for future functionality for more intelligent switching in battle.

`banned_moves` - list of moves for the battle engine to never select. Moves that are banned will not be selected in combat.


# Defaults
```yml
# Battle settings
# See readme for documentation: https://github.com/40Cakes/pokebot-gen3/wiki/%E2%9A%94-Battling-and-Pickup

# Pickup
pickup: true
pickup_threshold: 1
pickup_check_frequency: 5

# Battling
battle: false
battle_method: strongest  # `strongest`
faint_action: flee  # `stop`, `flee`, `rotate`
new_move: stop  # `stop`, `cancel`, `learn_best`
stop_evolution: true
replace_lead_battler: false
switch_strategy: first_available  # `first_available`
banned_moves:
  - None
  # 2-turn
  - Bounce
  - Dig
  - Dive
  - Fly
  - Sky Attack
  - Razor Wind
  - Doom Desire
  - Solar Beam
  # Inconsistent
  - Fake Out
  - False Swipe
  - Nature Power
  - Present
  - Destiny Bond
  - Wrap
  - Snore
  - Spit Up
  - Bide
  - Bind
  - Counter
  - Future Sight
  - Mirror Coat
  - Grudge
  - Snatch
  - Spite
  - Curse
  - Endeavor
  - Revenge
  - Assist
  - Focus Punch
  - Eruption
  - Flail
  # Ends battle
  - Roar
  - Whirlwind
  - Selfdestruct
  - Perish Song
  - Explosion
  - Memento
```