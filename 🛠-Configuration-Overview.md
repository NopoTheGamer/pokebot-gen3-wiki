The bot stores all profile information, such as save games, screenshots, statistics, etc. in the profile `profiles/<profile name>/`) folder, which is automatically created once you create a new profile.

Encounter statistics are saved into a sub-folder of your profile `profiles/<profile name>/stats/`.

Default configurations can be overridden by creating config files in a profile folder.

Configuration files are in `yml` format and are loaded and validated against a schema, at bot launch. Any changes made while the bot is running will need to be reloaded (default mapping is `Ctrl + C`.

The wiki page for for each configuration file will describe all options that are available, examples and defaults will also be shown.