With Discord integrations, you can receive shiny notifications, phase stats and milestones and more.

For privacy reasons, rich presence and webhooks are all **disabled** by default.

# Filename
[`discord.yml`](https://github.com/40Cakes/pokebot-gen3/blob/main/profiles/discord.yml)

# Information
## Discord rich presence
`rich_presence` - display information on your Discord profile such as game, route, total encounters, total shinies and encounter rate. Discord must be installed and signed in on the computer that is running the bot, and should only be enabled for a single bot profile.

## Discord webhooks
`global_webhook_url` - global Discord webhook URL, default webhook for all Discord webhooks unless specified otherwise
- ⚠ **Warning**: this webhook is considered sensitive! If you leak your webhook, anyone will be able to post in your channel
- **Edit Channel** > **Integrations** > **Webhooks** > **New Webhook** > **Copy Webhook URL** to generate a new webhook

`iv_format` - changes IV formatting displayed in messages, set to `basic` or `formatted`
- `basic`: <br>`HP: 31 | ATK: 31 | DEF: 31  | SPA: 31  | SPD: 31  | SPE: 31`

- `formatted`:
  ```
  ╔═══╤═══╤═══╤═══╤═══╤═══╗
  ║HP │ATK│DEF│SPA│SPD│SPE║
  ╠═══╪═══╪═══╪═══╪═══╪═══╣
  ║31 │31 │31 │31 │31 │31 ║
  ╚═══╧═══╧═══╧═══╧═══╧═══╝
  ```

`bot_id` - set to any string you want, this string is added to the footer of all Discord messages, it can be useful to identify bots if multiple are set to post in the same channel

### Webhook parameters
`enable` - toggle the webhook on/off

`webhook_url` - set to post specific message types to different channels, defaults to `global_webhook_url` if not set
- Commented out in config file by default, remove the leading `#` to uncomment

Each webhook type also supports pinging @users or @roles.

`ping_mode` - set to `user` or `role`
- Leave blank to disable pings

`ping_id` - set to user/role ID
- **Settings** > **Advanced** > Enable **Developer Mode** to enable Discord developer mode
- Right click **user/role** > **Copy ID**

#### Webhook types
`shiny_pokemon_encounter` - Shiny Pokémon encounters

![Discord_c0jrjiKGRE](https://github.com/40Cakes/pokebot-gen3/assets/16377135/e1706b41-5f89-40b4-918d-30d6e8fa92c2)

***

`pokemon_encounter_milestones` - Pokémon encounter milestones messages every `interval` encounters

![Discord_ObO28tVrPk](https://github.com/40Cakes/pokebot-gen3/assets/16377135/5c4698f0-07cf-4289-aa4e-6398f56422e0)

***

`shiny_pokemon_encounter_milestones` - Shiny Pokémon encounter milestones every `interval` encounters

![Discord_w7UfnPxlJZ](https://github.com/40Cakes/pokebot-gen3/assets/16377135/6d6e9b85-c8b4-4c15-8970-eb86e3b712ab)

***

`total_encounter_milestones` - Total encounter milestones every `interval` encounters

![Discord_ual6ZrsLNm](https://github.com/40Cakes/pokebot-gen3/assets/16377135/f6a82866-fbb3-4192-a771-f0b298bc12ec)

***

`phase_summary` - Phase summary, first summary at `first_interval`, then every `consequent_interval` after that

![Discord_plUyXtjnQt](https://github.com/40Cakes/pokebot-gen3/assets/16377135/573a638b-fe4e-4f16-95dd-31f0f750a517)

***

`anti_shiny_pokemon_encounter` - Anti-shiny Pokémon encounters
- Anti-shinies are just a bit of fun, they are mathematically, the complete opposite of a shiny
- An [SV](https://bulbapedia.bulbagarden.net/wiki/Personality_value#Shininess) of `65,528` to `65,535` is considered anti-shiny

![Discord_G2hvTZG21a](https://github.com/40Cakes/pokebot-gen3/assets/16377135/3f04d1cf-4040-4163-80d2-13cac84eed1f)

***

`custom_filter_pokemon_encounter` - Custom catch filter encounters

![image](https://github.com/40Cakes/pokebot-gen3/assets/16377135/9a52da68-5e3b-4f59-b222-18c4ed793c59)

# Defaults
```yml
rich_presence: false
global_webhook_url: ''
iv_format: formatted # `basic`, `formatted`
bot_id: PokéBot

# Shiny Pokémon encounters
shiny_pokemon_encounter:
  enable: false
  ping_mode:
  ping_id:
  #webhook_url:

# Pokémon encounter milestones
pokemon_encounter_milestones:
  enable: false
  interval: 10000
  ping_mode:
  ping_id:
  #webhook_url:

# Shiny Pokémon encounter milestones
shiny_pokemon_encounter_milestones:
  enable: false
  interval: 5
  ping_mode:
  ping_id:
  #webhook_url:

# Total encounter milestones
total_encounter_milestones:
  enable: false
  interval: 25000
  ping_mode:
  ping_id:
  #webhook_url:

# Phase summary
phase_summary:
  enable: false
  first_interval: 8192
  consequent_interval: 5000
  ping_mode:
  ping_id:
  #webhook_url:

# Anti-Shiny Pokémon encounters
anti_shiny_pokemon_encounter:
  enable: false
  ping_mode:
  ping_id:
  #webhook_url:

# Custom filter Pokémon encountered
custom_filter_pokemon_encounter:
  enable: false
  ping_mode:
  ping_id:
  #webhook_url:
```