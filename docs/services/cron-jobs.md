# Cron Jobs

Cron jobs are scheduled, ephemeral tasks that run on a predefined timeline using standard crontab syntax.

---

## Features
- **Distributed Overlap Protection**: Set `overlap = "forbid"` to ensure a new run will never start if the previous execution is still processing.
- **Independent Resource Quotas**: Dedicated CPU and memory allocated per run.
- **Execution Logs & Alerts**: Full stdout/stderr capture with automated alerts if a scheduled job exits with a non-zero code.

---

## Configuration Example

```toml
[[services]]
name = "invoice-generator"
type = "cron"
schedule = "0 2 * * *"
overlap = "forbid"
cmd = ["node", "scripts/generate-invoices.js"]

[services.resources]
vcpu = 2.0
memory = "2048MB"
```
