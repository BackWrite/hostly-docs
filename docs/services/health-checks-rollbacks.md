# Health Checks & Automated Rollbacks

Hostly guarantees zero-downtime deployments by verifying application readiness before cutting over user traffic.

---

## Probe Types
- **Readiness Probe**: Determines when a new deployment instance is ready to receive traffic.
- **Liveness Probe**: Periodically checks running instances. If an instance becomes unresponsive or enters a deadlock, Hostly restarts it automatically.

---

## Automated Rollback
If a new deployment fails 3 consecutive health check probes during blue-green deployment:
1. The new deployment is marked as failed.
2. User traffic is immediately routed back to the previously healthy deployment.
3. Zero customer downtime is incurred, and an alert is dispatched with the failure logs.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "api"
type = "web"

[services.health_check]
path = "/healthz"
interval_seconds = 5
timeout_seconds = 2
failure_threshold = 3
success_threshold = 1
```
