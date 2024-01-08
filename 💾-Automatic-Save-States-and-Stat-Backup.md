This file controls automatically making save states and making stat file backups

# Config Filename
[`auto_save.yml`](https://github.com/40Cakes/pokebot-gen3/blob/main/profiles/auto_save.yml)

# Defaults
```yml
stats:
  enable: false
  seconds_interval: 60
  
save_state:
  enable: false
  seconds_interval: 300
  save_as_backups: true # Having this as true saves the file in profiles\profile\states
```