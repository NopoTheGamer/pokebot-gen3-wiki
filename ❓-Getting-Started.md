# Supported Operating Systems
- Windows (**64-bit**)
- Linux (**64-bit**)
  - Note: only tested and confirmed working on **Ubuntu 23.04, 23.10** and **Debian 12**

# Download the Bot
## Stable Releases
Visit the [releases](https://github.com/40Cakes/pokebot-gen3/releases) page for the latest stable releases, download the **pokebot-vX.X.X.zip** file.

The bot has an auto-updater that will check for new stable releases, once a day.

## Dev Releases
To download the latest dev releases, go to the top of the repo page > click the green **Code** button > **Download ZIP**.

Alternatively, if you'd like to be able to easily pull the latest dev releases (may contain some bugs), use git:
- Install [GitHub Desktop](https://desktop.github.com/) (you don't need an account)
- Click **Clone a repository from the Internet...**
- Use repository URL `https://github.com/40Cakes/pokebot-gen3.git` and choose a save location on your PC
- Click **Clone**
- Any time there's a new update, you can pull the latest changes by clicking **Fetch origin**, then **Pull origin**

# Requirements
- [Python 3.12](https://www.python.org/downloads/release/python-3120/) (**64-bit**)
- **Linux** only: Install the following packages with `apt` or appropriate package manager: `sudo apt install python3-tk libmgba0.10 portaudio19-dev`
- **Note**: running the bot will **automatically** install required Python packages and download + extract [libmgba](https://github.com/hanzi/libmgba-py) - if you're using Python for any other projects, consider using a [venv](https://docs.python.org/3/library/venv.html) to isolate these packages from your base environment

## Optional
- [Windows Terminal](https://github.com/microsoft/terminal/releases) - recommended for full 🌈<span style="color:#FF0000">c</span><span style="color:#FF7F00">o</span><span style="color:#FFFF00">l</span><span style="color:#00FF00">o</span><span style="color:#00FFFF">u</span><span style="color:#CF9FFF">r</span>🌈 and  ✨emoji support✨ in the console output
- [Notepad++](https://notepad-plus-plus.org/) - recommended for syntax highlighting while editing `.yml` config files

# Run the Bot
- Place some **official** Pokémon .gba ROMs into the `roms/` folder
- Double click `pokebot.py` or run `python pokebot.py` in a terminal and follow the on-screen steps to create and/or select a profile

For help and support, reach out in Discord [#bot-support-libmgba❔](https://discord.com/channels/1057088810950860850/1139190426834833528) or [raise an issue](https://github.com/40Cakes/pokebot-gen3/issues) on this repository.

The bot ships with the default mGBA input mapping, see [here](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%8E%AE-Emulator-Input-Mapping) for the default mapping, or customise them to your preference.

The bot will pause once a shiny is encountered. You **must** ensure you are able to escape battle **100% of the time**, otherwise the bot will get stuck. Auto-catching and other features will be added in due time.

# Tips/Tricks
- Set **TEXT SPEED** to **FAST**
- Set **BATTLE SCENE** to **OFF**
- Utilise [repel tricks](https://bulbapedia.bulbagarden.net/wiki/Appendix:Repel_trick) to boost encounter rates of target Pokémon
- Using modes [Spin](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%94%84-Spin) or [Bunny Hop](https://github.com/40Cakes/pokebot-gen3/wiki/%F0%9F%9A%B2-Bunny-Hop) and repels will become effectively infinite + steps won't be counted in Safari Zone
- Use a lead Pokémon with encounter rate boosting [abilities](https://bulbapedia.bulbagarden.net/wiki/Category:Abilities_that_affect_appearance_of_wild_Pok%C3%A9mon), such as **[Illuminate](https://bulbapedia.bulbagarden.net/wiki/Illuminate_(Ability))**
- Use a lead Pokémon with a [short cry](https://docs.google.com/spreadsheets/d/1rmtNdlIXiif1Sz20i-9mfhFdoqb1VnAOIntlr3tnPeU)
- Use a lead Pokémon with a single character nickname
- Don't use a shiny lead Pokémon (shiny animation takes a few frames at the start of every battle)
