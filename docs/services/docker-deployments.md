# Docker & Custom OCI Containers

Deploy any application packaged as a Dockerfile or pre-built OCI container image.

---

## Features
- **Multi-Stage Build Support**: Automated layer caching speeds up subsequent builds by up to 10x.
- **Private Container Registry Integration**: Pull private images directly from Docker Hub, GitHub Container Registry (GHCR), AWS ECR, or Google Artifact Registry.
- **Rootless Execution**: Containers run securely with unprivileged user namespaces and hard memory ceilings.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "custom-service"
type = "web"
routes = ["custom.hostly.dev"]

[services.build]
dockerfile = "deploy/Dockerfile.prod"
context = "."
args = { ENVIRONMENT = "production" }
```
