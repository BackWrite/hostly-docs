# Autoscaling & Performance Telemetry

Automatically scale your service replicas in response to incoming traffic demand.

---

## Features
- **Horizontal Pod Autoscaling (HPA)**: Scale between a configured minimum and maximum number of replicas based on CPU, memory, or concurrent HTTP requests.
- **Sub-Second Metric Dashboards**: View live CPU, RAM, network I/O, and HTTP response code percentiles (p50, p95, p99) updated every second.
- **Scale to Zero (Preview/Dev)**: Save money by sleeping inactive preview services and waking them upon the next incoming HTTP request in $<250\text{ ms}$.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "checkout-api"
type = "web"
routes = ["checkout.hostly.dev"]

[services.scaling]
min_replicas = 2
max_replicas = 20
target_cpu_percent = 75
target_concurrent_requests = 100
```
