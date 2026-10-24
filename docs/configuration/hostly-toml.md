# `hostly.toml` Configuration Reference

`hostly.toml` is the declarative configuration file placed at the root of your repository to define services, databases, environment variables, and build settings.

---

## Minimal Specification

```toml
[project]
name = "my-application"

[[services]]
name = "web"
type = "web"
routes = ["app.hostly.dev"]
```

---

## Complete Specification

```toml
[project]
name = "enterprise-api"
version = "2027-01-01"

[build]
shared_immutable = true
strategy = "buildpack"

[[services]]
name = "api"
type = "web"
routes = ["api.hostly.dev", "api.example.com"]
health_check = { path = "/healthz", interval = 5, timeout = 2 }

[services.resources]
vcpu = 2.0
memory = "2048MB"

[services.env]
NODE_ENV = "production"
DATABASE_URL = "${primary-db.CONNECTION_STRING}"
CACHE_URL = "${redis-cache.CONNECTION_STRING}"

[[services]]
name = "queue-worker"
type = "worker"
cmd = ["npm", "run", "worker"]

[services.resources]
vcpu = 1.0
memory = "1024MB"

[[services]]
name = "daily-cleanup"
type = "cron"
schedule = "0 3 * * *"
overlap = "forbid"
cmd = ["npm", "run", "cleanup"]

[[databases]]
name = "primary-db"
engine = "postgres"
plan = "production-ha"

[[databases]]
name = "redis-cache"
engine = "valkey"
plan = "standard"
```
