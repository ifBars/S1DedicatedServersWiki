## Networking

Checklist:

- Port in `serverPort` open on firewall/NAT.
- Logs show Tugboat server started and loopback client connected.
- Clients use correct public IP/port to connect.

### Port forwarding
- Forward `serverPort` (default `38465`) on your router to the server's local IP. Forward TCP and UDP.
- Allow the same port through your OS firewall.
- Verify from outside your network using an online port check tool.

Guides:

- [How to Forward Ports on Your Router (How‑To Geek)](https://www.howtogeek.com/66214/how-to-forward-ports-on-your-router/)
- [Router‑specific port forwarding guides (PortForward.com)](https://portforward.com/router.htm)

If you cannot forward ports (CGNAT/ISP restrictions), consider hosting on a VPS or having a friend host it for you.


