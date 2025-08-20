---
title: Messaging API
---

Lightweight client↔server messaging is provided by `DedicatedServerMod.Shared.CustomMessaging`. Mods can send arbitrary string payloads and subscribe to receive events without patching networking internals.

## Send helpers

- Server→Client: `CustomMessaging.SendToClient(NetworkConnection, string command, string data = "")`
- Server→Clients: `CustomMessaging.BroadcastToClients(string command, string data = "")`
- Client→Server: `CustomMessaging.SendToServer(string command, string data = "")`

Payloads are strings; use JSON if you need structure.

## Receive hooks

- Client side: `CustomMessaging.ClientMessageReceived += (command, data) => { ... }`
- Server side: `CustomMessaging.ServerMessageReceived += (conn, command, data) => { ... }`

If you implement `IClientMod`/`IServerMod`, message forwarding is also exposed via `OnCustomMessage(...)` when `ModManager` wiring is active. Prefer the explicit events for connection context on server.

Server note: to receive `OnCustomMessage(...)` on server mods via forwarding, ensure wiring is enabled:

```csharp
// Call once during init if you want OnCustomMessage to receive forwarded messages
ModManager.EnsureServerMessageForwarding();
```

## Example: round-trip

Client sends a request and server replies with JSON:

```csharp
// Client
CustomMessaging.SendToServer("request_org_info", "");
CustomMessaging.ClientMessageReceived += (cmd, data) =>
{
    if (cmd == "org_info")
    {
        var info = JsonConvert.DeserializeObject<OrgInfo>(data);
        // update UI
    }
};

// Server
CustomMessaging.ServerMessageReceived += (conn, cmd, data) =>
{
    if (cmd == "request_org_info")
    {
        var payload = JsonConvert.SerializeObject(BuildOrgInfo(conn));
        CustomMessaging.SendToClient(conn, "org_info", payload);
    }
};
```

## Best practices

- Keep commands namespaced, e.g. `yourmod_feature_action`.
- Validate server-side permissions before acting.
- Avoid large payloads; prefer small, frequent updates.
- Use `OnClientPlayerReady()` before sending from client to ensure messaging is ready.


