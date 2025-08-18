## Troubleshooting

### Server won’t start: save path not set
- Error mentions `saveGamePath` not configured.
- Edit `server_config.json` and set `saveGamePath` to the world folder. Use double backslashes on Windows.

### Server saves to DevSave
- Ensure you set `saveGamePath`.
- Check logs for: “Restored loaded save path: …” after the Main scene loads.
- Open an issue on the [GitHub repository](https://github.com/ifBars/S1DedicatedServers/issues).

### Clients stuck or time freezes at 4:00
- Ensure `timeNeverStops` is true.
- Check the client logs for 1 minute based time syncs. (Time UI will be stuck on 4AM between 4 and 7AM)
- Open an issue on the [GitHub repository](https://github.com/ifBars/S1DedicatedServers/issues).

### Console says you lack permission
- You may need to add your SteamID64 to `operators` and/or `admins` in `server_config.json`.
- Restart the server

### Connection/port problems
- Confirm that you forwarded the correct port in `serverPort` in `server_config.json`.
- Confirm port in `serverPort` is open on firewall/NAT.
- Check logs for Tugboat startup and that the loopback client connects.


