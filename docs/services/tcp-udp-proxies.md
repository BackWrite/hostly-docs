# Non-HTTP TCP & UDP Proxies

Hostly supports non-HTTP services including real-time WebSockets, gRPC, game servers, IoT gateways, and custom TCP/UDP protocols.

---

## Features
- **Dedicated Port Allocation**: Allocate static public ports (e.g. `tcp://hostly.dev:25565`).
- **Low-Latency Direct Routing**: Network packets bypass HTTP proxies and route directly to your running workload.
- **DDoS Mitigation**: Hardware-level packet rate limiting protects against UDP amplification and TCP SYN floods.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "game-server"
type = "tcp"
public_port = 25565
target_port = 25565
protocol = "tcp"

[services.resources]
vcpu = 4.0
memory = "8192MB"
```
