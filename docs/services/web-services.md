# Web Services

Web services are long-running applications with public HTTP/HTTPS endpoints.

---

## Features
- **Instant SSL/TLS**: Automated Let's Encrypt certificates for all assigned domains and custom domains.
- **Zero-Downtime Blue-Green Deploys**: New versions receive traffic only after passing configured health checks.
- **Custom Domains**: Point your apex domain (`example.com`) or subdomains (`app.example.com`) with a simple CNAME.
- **Auto-Rollback**: If a new deployment fails health checks, Hostly automatically retains the previous healthy deployment without customer disruption.

---

## Configuration Example

```toml
[[services]]
name = "web-frontend"
type = "web"
routes = ["app.hostly.dev", "app.example.com"]
health_check = { path = "/api/health", interval = 5, timeout = 2 }

[services.resources]
vcpu = 1.0
memory = "1024MB"
```
