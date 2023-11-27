# Operating Systems

- Windows (**64-bit**)
- Linux (**64-bit**)
  - Note: only tested and confirmed working on **Ubuntu 23.04, 23.10** and **Debian 12**

# Download the Bot
To download the latest bot from GitHub, go to the top of the page > click the green **Code** button > **Download ZIP**.

Alternatively, if you'd like to be able to easily pull the latest updates without re-downloading the entire ZIP:
- Install [GitHub Desktop](https://desktop.github.com/) (you don't need an account)
- Click **Clone a repository from the Internet...**
- Use repository URL `https://github.com/40Cakes/pokebot-gen3.git` and choose a save location on your PC
- Click **Clone**
- Any time there's a new update, you can pull the latest changes by clicking **Fetch origin**, then **Pull origin**

# Requirements
- [Python 3.12](https://www.python.org/downloads/release/python-3120/) (**64-bit**)
- **Linux** only: Install the following packages with `apt` or appropriate package manager: `sudo apt install python3-tk libmgba0.10 portaudio19-dev`
- **Note**: running the bot will **automatically** install required Python packages and download + extract [libmgba](https://github.com/hanzi/libmgba-py) - if you're using Python for any other projects, consider using a [venv](https://docs.python.org/3/library/venv.html) to isolate these packages from your base environment

# Optional
- [Windows Terminal](https://github.com/microsoft/terminal/releases) - recommended for full 🌈<span style="color:#FF0000">c</span><span style="color:#FF7F00">o</span><span style="color:#FFFF00">l</span><span style="color:#00FF00">o</span><span style="color:#00FFFF">u</span><span style="color:#CF9FFF">r</span>🌈 and  ✨emoji support✨ in the console output
- [Notepad++](https://notepad-plus-plus.org/) - recommended for syntax highlighting while editing `.yml` config files
