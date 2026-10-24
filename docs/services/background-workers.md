# Background Workers

Background workers are persistent, headless processes that execute asynchronous jobs, process message queues, or stream data pipelines.

---

## Features
- **No Public Attack Surface**: Workers do not expose public HTTP ports and run securely within your private network.
- **Automatic Crash Restarts**: If a worker crashes or encounters an unhandled exception, Hostly restarts it immediately.
- **Private Database Access**: Securely connects to your managed PostgreSQL or Valkey instances over private networking.

---

## Configuration Example

```toml
[[services]]
name = "email-worker"
type = "worker"
cmd = ["python", "worker.py"]

[services.resources]
vcpu = 1.0
memory = "1024MB"

[services.env]
QUEUE_NAME = "transactional-emails"
DATABASE_URL = "${primary-db.CONNECTION_STRING}"
```
