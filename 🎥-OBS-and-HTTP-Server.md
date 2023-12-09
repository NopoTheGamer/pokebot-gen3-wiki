This configuration can be used to drive stream overlays or web UIs.

**Note**: These are fairly buggy and WIP + data formats from the HTTP server may change without notice.

# Filename
[`obs.yml`](https://github.com/40Cakes/pokebot-gen3/blob/main/profiles/obs.yml)

# Information
## OBS
### OBS WebSocket Server Settings
The `obs_websocket` config will allow the bot to send commands to OBS via WebSockets,
see [here](https://github.com/obsproject/obs-websocket) for more information on OBS WebSockets.

Enable WebSockets in **OBS** > **Tools** > **Websocket Server Settings** > **Enable WebSocket Server**

`host` - hostname/IP address OBS WebSockets is listening on

`port` - TCP port OBS WebSockets is listening on

`password` - password to authenticate to WebSocket server (**required**)

### OBS WebSocket Parameters
`shiny_delay` - delay catching a shiny encounter by `n` frames, useful to give you viewers some time to react before saving a replay

`discord_delay` - delay Discord webhooks by `n` seconds, prevent spoilers if there is a stream delay

`screenshot` - take OBS screenshot of shiny encounter
- **Note**: **OBS** > **Settings** > **Hotkeys** > **Screenshot Output** must be set to **Ctrl + F11**
- The bot does **not** emulate keystrokes, it simply sends a `TriggerHotkeyByKeySequence` (**Ctrl + F11**) WebSocket command
- Screenshot is taken after `shiny_delay` to allow stream overlays to update

`replay_buffer` - save OBS replay buffer after `replay_buffer_delay`
- **Note**: **OBS** > **Settings** > **Hotkeys** > **Replay Buffer** > **Save Replay** must set to **Ctrl + F12**
- The bot does **not** emulate keystrokes, it simply sends a `TriggerHotkeyByKeySequence` (**Ctrl + F12**) WebSocket command

`replay_buffer_delay` - delay saving OBS replay buffer by `n` seconds
- Runs in a separate thread and will not pause main bot thread
- If the replay buffer is long enough, it will also capture some encounters after the shiny encounter

`discord_webhook_url` - Discord webhook URL to post OBS `screenshot`, after a shiny encounter

`replay_dir` - OBS screenshot/replay buffer folder
- **OBS** > **Settings** > **Output** > **Recording** > **Recording Path**
- Relative folder to `pokebot.py`, this is used to post stream `screenshot` to Discord if `discord_webhook_url` is set

## HTTP server
The `http_server` config will enable a Flask HTTP server, which can be used to retrieve data and drive stream overlays.

`enable` - toggle web server on/off

`ip` - IP address for server to listen on

`port` - TCP port for server to listen on
- Port must be unique for each bot instance

### HTTP Endpoints
All HTTP responses are in JSON format.

`GET /player` - returns contains rarely-changing player data such as name, TID, SID etc.

`GET /player_avatar` - returns contains the on-map character data such as map bank, map ID, X/Y coordinates

`GET /items` - returns all a list of all items in the bag and PC, and their quantities

`GET /party` - returns a detailed list of all Pokémon in the party

`GET /map` - returns data about the map and current tile that the player avatar is standing on

`GET /encounter_log` returns a detailed list of the recent 10 Pokémon encounters

`GET /shiny_log` returns a detailed list of all shiny Pokémon encounters (`shiny_log.json`)

`GET /stats` returns the phase and total statistics (`totals.json`)

`GET /encounter_rate` returns the current encounter rate (encounters per hour)

`GET /event_flags` returns all event flags for the current save file (optional parameter `?flag=FLAG_NAME` to get a specific flag)

`GET /emulator` returns information about the emulator core + the current loaded game/profile

`GET /game_state` - returns current game state information

`GET /map/<int:map_group>/<int:map_number>` - returns detailed information about a [specific map](https://github.com/40Cakes/pokebot-gen3/blob/main/modules/data/map.py)

`POST /emulator` allows changing some settings for the emulator. This requires a JSON object as payload, with the 
following allowed keys: `emulation_speed`, `bot_mode`, `video_enabled`, `audio_enabled`.

`GET /fps` returns a list of emulator FPS (frames per second), in intervals of 1 second, for the previous 60 seconds

`GET /stream_events` is a way to continuously receive updates from the bot in the form of server-sent events. See
[its own Readme](https://github.com/40Cakes/pokebot-gen3/blob/master/modules/web/Readme.md) for more details.

`GET /stream_video` can be used as a source in HTML `<img/>` tags to receive a live video feed of the bot. It accepts
an optional query parameter `fps` which can indicate the update rate of the image (default: `30`.) For example:
`<img src="/stream_video?fps=5"/>` to get a 5 fps stream. A lower number means less impact on bot performance.


# Defaults
```yml
obs_websocket:
  host: 127.0.0.1
  port: 4455
  password: password

shiny_delay: 0
discord_delay: 0
screenshot: false
replay_buffer: false
replay_buffer_delay: 0
discord_webhook_url:
replay_dir: "./stream/replays/"

http_server:
  enable: false
  ip: 127.0.0.1
  port: 8888
```