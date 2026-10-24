# Serverless & Edge Functions

Execute code on demand in response to HTTP events with sub-millisecond cold starts and automatic scaling down to zero.

---

## Features
- **Sub-Millisecond Cold Starts**: Powered by ultra-fast isolated runtimes executing in $<500\ \mu\text{s}$.
- **Zero Cost Idle**: You pay strictly for the exact execution duration (measured in milliseconds).
- **Polyglot Execution**: Write functions in TypeScript, JavaScript, Python, Go, or Rust.
- **Integrated Environment Secrets**: Seamless access to your organization's encrypted secrets and managed database connection strings.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "image-resizer"
type = "function"
routes = ["api.hostly.dev/images/*"]
runtime = "nodejs-22"
entrypoint = "handlers/resize.js"
memory = "512MB"
timeout_seconds = 10
```
