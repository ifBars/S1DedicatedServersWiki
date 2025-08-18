## Configuration

The server reads settings from `server_config.json` (created on first run under the MelonLoader user data directory).

### Current limitations / placeholders
- The following settings are present in `server_config.json` but are not yet integrated into server behavior. Changing them currently has no effect and they are reserved for future updates:
  - `serverName`
  - `serverDescription`
  - `publicServer`
  - `enableMotd`, `motdMessage`
  - `welcomeMessage`
  - `showPlayerJoinMessages`, `showPlayerLeaveMessages`
  - `enablePerformanceMonitoring`

These fields will be wired up in future versions (names, scope, and behavior may change).

### Required
- `saveGamePath`: Full path to the save folder to host.
  - Windows: escape backslashes: `C:\\Users\\you\\AppData\\LocalLow\\TVGS\\Schedule I\\Saves\\<SteamID>\\SaveGame_1`
  - Must contain files like `Game.json`, `Metadata.json`, etc.

### Recommended
- `serverPort` (default 38465)
- `serverName`, `serverDescription`
- `publicServer` (true/false) 

### Access control
- `operators`: Full permissions and all commands.
- `admins`: Limited commands defined by `allowedCommands`; denied those in `restrictedCommands`.
- `bannedPlayers`: SteamID64 strings blocked from joining.

### Auto-save
- `autoSaveEnabled`: true/false
- `autoSaveIntervalMinutes`: minutes between periodic saves
- `autoSaveOnPlayerJoin` / `autoSaveOnPlayerLeave`

### Gameplay
- `ignoreGhostHostForSleep`: Ignore loopback client in sleep checks.
- `timeNeverStops`: Prevents 4AM freeze; time continues overnight.
- `timeProgressionMultiplier`: 1.0 is normal speed.

### Starting the server
- Use `start_server.bat` from `server.zip` to launch the dedicated server install.

The server will refuse to start if `saveGamePath` is not set.


### Networking (port forwarding)
- To allow players outside your local network to connect, you must port forward the value of `serverPort` (default `38465`) from your router to the server machine's local IP.
- Protocol: forward both TCP and UDP.
- Ensure your OS firewall allows inbound connections on the forwarded port.
- Players should connect using your public IP and the forwarded port.

Helpful guides:

- [Beginners Guide to Port Forwarding (Tinkernut)](https://www.youtube.com/watch?v=jfSLxs40sIw)
- [Router‑specific port forwarding guides (PortForward.com)](https://portforward.com/router.htm)

Notes:

- Some ISPs use CGNAT; port forwarding may not work. In that case, request a public IPv4, use IPv6, or host on a VPS.


