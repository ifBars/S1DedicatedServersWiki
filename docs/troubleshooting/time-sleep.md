## Time & Sleep

- Time stuck at 04:00: set `timeNeverStops` true.
- Clients out-of-sync: Wait 1 minute and check again, if still out of sync, open an issue on the [GitHub repository](https://github.com/ifBars/S1DedicatedServers/issues).
- Sleeping says waiting for players: ensure it is 4AM; ensure `ignoreGhostHostForSleep` true so loopback client is ignored. (Sleeping in a bed will likely break the client sync, it is recommended to use the timeNeverStops setting instead)


