# Ephemeral Preview Environments

Automatically spin up isolated, fully functional staging environments for every Pull Request on GitHub or GitLab.

---

## Features
- **Zero-Friction Collaboration**: Share unique preview URLs (e.g. `https://pr-42.preview.hostly.dev`) with designers, PMs, and stakeholders before merging code.
- **Isolated Branch Databases**: Automatically fork or provision fresh ephemeral database schemas for pull request testing.
- **Automatic Lifecycle Teardown**: Environments are instantly destroyed when the Pull Request is merged or closed, preventing wasted spend.
- **GitHub Bot Integration**: Hostly posts deployment status, build logs, and live preview URLs directly as PR comments.

---

## Configuration Example (`hostly.toml`)

```toml
[preview_environments]
enabled = true
auto_deploy_pull_requests = true
expire_after_days_inactive = 7
database_strategy = "fork_staging"
```
