# Quickstart Guide

Deploy your first application on Hostly in under two minutes.

---

## 1. Install the Hostly CLI

Install the official Hostly CLI tool for your platform:

```bash
# macOS (Homebrew)
brew install hostly/tap/hostly

# Linux / curl
curl -fsSL https://cli.hostly.dev/install.sh | bash

# Windows (winget)
winget install Hostly.CLI
```

Verify the installation:
```bash
hostly --version
```

---

## 2. Authenticate Your Terminal

Log in to your Hostly account:

```bash
hostly login
```

This opens your browser to authorize your session securely via OAuth 2.1 PKCE.

---

## 3. Initialize Your Project

Navigate to your application repository (Node.js, Python, Go, Rust, PHP, or Docker):

```bash
cd my-app
hostly init
```

The CLI inspects your project, automatically detects your framework, and generates a minimal `hostly.toml` file:

```toml
[project]
name = "my-app"

[[services]]
name = "web"
type = "web"
routes = ["my-app.hostly.dev"]
health_check = { path = "/" }

[services.resources]
vcpu = 1.0
memory = "1024MB"
```

---

## 4. Deploy to the Cloud

Trigger a live deployment:

```bash
hostly deploy
```

Hostly uses fast content-defined chunking (FastCDC) to upload only the changed lines of code, builds your container, runs health checks, provisions an SSL certificate, and makes your app live at `https://my-app.hostly.dev`.

---

## 5. View Real-Time Logs

Tail live production logs directly in your terminal:

```bash
hostly logs --follow
```
