# Private Services & Internal Mesh

Deploy internal backend microservices that communicate securely over private networking without exposing ports to the public internet.

---

## Features
- **Zero Public Attack Surface**: No public IP or domain assigned; completely unreachable from the external web.
- **Encrypted Internal Mesh**: Microservices communicate over private WireGuard networking using internal DNS.
- **Sub-Millisecond Internal Latency**: Fast, secure communication between internal APIs, databases, and worker pipelines.

---

## Service Discovery & Addressing

Internal services resolve automatically using the pattern:
```
http://<service-name>.<project-name>.hostly.internal:<port>
```

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "payment-processor"
type = "private"
port = 8080

[services.resources]
vcpu = 2.0
memory = "2048MB"
```
