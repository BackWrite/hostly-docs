# Managed Valkey / Redis

Hostly provides managed Valkey 8.0 (the high-performance, open-source Linux Foundation engine compatible with Redis).

---

## Use Cases
- High-speed session storage.
- In-memory API response caching.
- Low-latency pub/sub message brokers and task queues.

---

## Configuration Example

```toml
[[databases]]
name = "cache"
engine = "valkey"
plan = "standard"

[[services]]
name = "api"
type = "web"
[services.env]
REDIS_URL = "${cache.CONNECTION_STRING}"
```
