# Hostly CLI Reference

The Hostly CLI (`hostly`) allows you to manage projects, deploy code, and inspect logs directly from your terminal.

---

## Core Commands

| Command | Description |
| :--- | :--- |
| `hostly login` | Authenticate your terminal with your Hostly account via browser |
| `hostly init` | Initialize a new `hostly.toml` in the current repository |
| `hostly deploy` | Upload code delta and trigger a cloud build and deployment |
| `hostly logs` | Stream live production logs from your active services |
| `hostly env pull` | Download environment variables to a local `.env` file |
| `hostly env set KEY=VAL` | Set an encrypted environment variable on the cloud project |
| `hostly status` | Check deployment status and health checks |
