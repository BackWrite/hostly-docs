# Environment Variables & Secrets Management

Securely manage sensitive API keys, database credentials, and application configuration.

---

## Features
- **Envelope Encryption**: Secrets are encrypted using hardware-backed keys before being written to disk.
- **Branch & Environment Inheritance**: Set global secrets for your organization, or override them for `production`, `staging`, and `preview` environments.
- **Automatic Reference Expansion**: Reference outputs from other services and databases automatically:
  ```
  DATABASE_URL = "${primary-db.CONNECTION_STRING}"
  REDIS_URL = "${cache.CONNECTION_STRING}"
  ```

---

## Managing Secrets via CLI

```bash
# Set an encrypted secret
hostly env set STRIPE_SECRET_KEY="sk_live_..."

# Pull environment variables for local testing
hostly env pull .env.local
```
