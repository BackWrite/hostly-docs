# Hostly Developer Documentation

> **Official Developer Documentation & User Guides for Hostly**  
> **Global Web:** [https://hostly.dev](https://hostly.dev) · **Console:** [https://console.hostly.dev](https://console.hostly.dev)  
> **East Africa Web:** [https://hostly.co.ke](https://hostly.co.ke) · **Status:** [https://status.hostly.dev](https://status.hostly.dev)

---

## Welcome to Hostly

**Hostly** is a fast, developer-friendly cloud application platform designed to build, deploy, and scale web applications, background workers, and managed databases with zero DevOps overhead.

Whether you are pushing a Next.js frontend, a Python FastAPI backend, a Go microservice, or provisioning a managed PostgreSQL database, Hostly gives you instant global deployments, automated SSL, and transparent per-second billing.

---

## Documentation Index

### 🚀 Getting Started
- **[Quickstart Guide](./docs/getting-started/quickstart.md)**: Deploy your first project in 60 seconds using the Hostly CLI or Git.

### ⚙️ Configuration & Infrastructure as Code
- **[`hostly.toml` Reference](./docs/configuration/hostly-toml.md)**: Declarative configuration for services, databases, environment variables, and build settings.

### 📦 Services & Compute Primitives
Hostly provides a complete suite of execution primitives for modern architectures:
- **[Web Services](./docs/services/web-services.md)**: Public web apps, HTTP/2 & HTTP/3, custom domains, and instant Let's Encrypt SSL.
- **[Background Workers](./docs/services/background-workers.md)**: Headless queue consumers and asynchronous data processors.
- **[Cron Jobs](./docs/services/cron-jobs.md)**: Scheduled tasks with automated overlap prevention and failure alerts.
- **[Static Sites & Jamstack](./docs/services/static-sites.md)**: Ultra-fast static asset hosting with global anycast edge caching.
- **[Serverless Functions](./docs/services/serverless-functions.md)**: Sub-millisecond cold starts and event-driven functions.
- **[Ephemeral Preview Environments](./docs/services/preview-environments.md)**: Automated staging branches for every Pull Request.
- **[Private Services](./docs/services/private-services.md)**: Zero-attack-surface microservices over encrypted private networking.
- **[Docker & Custom Containers](./docs/services/docker-deployments.md)**: Custom Dockerfile & OCI container deployments with multi-stage layer caching.
- **[Non-HTTP TCP/UDP Proxies](./docs/services/tcp-udp-proxies.md)**: Real-time WebSockets, gRPC, and custom TCP/UDP routing.
- **[S3 Storage Buckets](./docs/services/storage-buckets.md)**: S3-compatible object storage with zero egress markups.
- **[Persistent Disks](./docs/services/persistent-disks.md)**: Attached high-IOPS NVMe block storage surviving deploys.
- **[AI Model Inference & LLM Serving](./docs/services/ai-inference-endpoints.md)**: High-performance compute instances for open-source AI models.
- **[Custom Domains & Automated SSL](./docs/services/custom-domains-ssl.md)**: Apex and wildcard domain routing with instant TLS.
- **[Autoscaling & Telemetry](./docs/services/autoscaling-metrics.md)**: Horizontal and vertical autoscaling with live performance metrics.
- **[Health Checks & Rollbacks](./docs/services/health-checks-rollbacks.md)**: Zero-downtime blue-green deployments and automated failover.
- **[Environment Variables & Secrets](./docs/services/environment-variables.md)**: Encrypted secret vault with branch inheritance.

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
- **Global Portal:** [https://hostly.dev](https://hostly.dev)
- **East Africa Portal:** [https://hostly.co.ke](https://hostly.co.ke)
- **Discord:** [Join Hostly Community](https://discord.gg/hostly)
- **Support Email:** `support@hostly.dev` / `support@hostly.co.ke`
