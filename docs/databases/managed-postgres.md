# Managed PostgreSQL

Hostly provides fully managed, production-ready PostgreSQL with built-in connection pooling and point-in-time recovery.

---

## Key Benefits
- **Built-in PgBouncer**: Prevents connection exhaustion by pooling connections in transaction mode on port 6432.
- **Automated Streaming Backups**: Continuous WAL backups with point-in-time recovery.
- **One-Click Scaling**: Scale vCPU, RAM, and disk storage without downtime.

---

## Connection Strings

When you link a database to a service in `hostly.toml`, Hostly automatically injects the connection string:

```toml
[[databases]]
name = "primary-db"
engine = "postgres"
plan = "production"

[[services]]
name = "api"
type = "web"
[services.env]
DATABASE_URL = "${primary-db.CONNECTION_STRING}"
```
