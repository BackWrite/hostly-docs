# Hostly Documentation

> **Official Developer Documentation & Guides for Hostly**  
> **Global Web:** [https://hostly.dev](https://hostly.dev) · **Console:** [https://console.hostly.dev](https://console.hostly.dev)  
> **East Africa Web:** [https://hostly.co.ke](https://hostly.co.ke) · **Status:** [https://status.hostly.dev](https://status.hostly.dev)

---

## Welcome to Hostly

**Hostly** is a fast, developer-friendly cloud platform designed to build, deploy, and scale web applications, background workers, and managed databases with zero DevOps overhead.

Whether you are pushing a Next.js frontend, a Python FastAPI backend, a Go microservice, or provisioning a managed PostgreSQL database, Hostly gives you instant global deployments, automated SSL, and transparent per-second billing.

---

## Documentation Index

### 🚀 Getting Started
- **[Quickstart Guide](./docs/getting-started/quickstart.md)**: Deploy your first project in 60 seconds using the Hostly CLI or Git.

### ⚙️ Configuration & Infrastructure as Code
- **[`hostly.toml` Reference](./docs/configuration/hostly-toml.md)**: Declarative configuration for services, databases, environment variables, and build settings.

### 📦 Services & Compute
- **[Web Services](./docs/services/web-services.md)**: Public web apps, HTTP/2 & HTTP/3, custom domains, and instant Let's Encrypt SSL.
- **[Background Workers](./docs/services/background-workers.md)**: Headless queue consumers and asynchronous data processors.
- **[Cron Jobs](./docs/services/cron-jobs.md)**: Scheduled tasks with automated overlap prevention and failure alerts.

### 🗄️ Managed Databases
- **[Managed PostgreSQL](./docs/databases/managed-postgres.md)**: High-performance PostgreSQL with built-in connection pooling and automated backups.
- **[Managed Valkey / Redis](./docs/databases/managed-valkey.md)**: In-memory caching and message queues.

### 🛠️ Developer Tooling
- **[Hostly CLI Reference](./docs/cli/reference.md)**: One-command deployments, environment variable sync, and real-time log streaming.

### 💳 Billing & Plans
- **[Billing & Pricing Overview](./docs/billing/overview.md)**: Simple per-second pricing, multi-currency support (USD, KES), prepaid wallets, and hard budget caps.

---

## Quick Example: `hostly.toml`

Add a `hostly.toml` file to the root of your repository:

```toml
[project]
name = "my-web-app"

[[services]]
name = "api"
type = "web"
routes = ["api.hostly.dev"]
health_check = { path = "/healthz" }

[services.resources]
vcpu = 1.0
memory = "1024MB"

[[databases]]
name = "primary-db"
engine = "postgres"
```

Then deploy with one command:

```bash
hostly deploy
```

---

## Community & Support
- **Discord:** [Join Hostly Community](https://discord.gg/hostly)
- **Twitter / X:** [@HostlyCloud](https://x.com/hostlycloud)
- **Support Email:** `support@hostly.dev` / `support@hostly.co.ke`
