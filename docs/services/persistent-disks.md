# Attached Persistent Disks

Attach persistent, high-IOPS NVMe block storage volumes to your web services and background workers.

---

## Features
- **Data Persistence Across Deploys**: Your data survives code updates, container restarts, and host maintenance.
- **Automatic Multi-Zone Failover**: If a physical server fails, your persistent volume detaches and re-attaches to a healthy node in $<45\text{ seconds}$.
- **Online Volume Resizing**: Expand volume size dynamically from the dashboard or CLI without taking your application offline.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "cms"
type = "web"
routes = ["cms.hostly.dev"]

[[services.disks]]
name = "uploads"
mount_path = "/var/www/uploads"
size = "50GB"
```
