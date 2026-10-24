# Static Sites & Jamstack Hosting

Hostly provides global, high-speed static asset and Jamstack website hosting distributed across anycast edge points of presence.

---

## Supported Frameworks
- Next.js (Static Export / SSG)
- Vite, React, Vue, SvelteKit, Astro
- Hugo, Jekyll, Docusaurus, Eleventy
- Plain HTML, CSS, JavaScript

---

## Features
- **Global Anycast Edge**: Content is cached and served from the nearest global edge node with sub-10ms response times.
- **Automated Compression**: Brotli and Gzip compression applied automatically.
- **Custom Clean URLs**: Automated trailing slash handling and redirect rules.
- **Zero Compute Cost When Idle**: Static assets incur zero CPU charges, only standard disk storage and bandwidth.

---

## Configuration Example (`hostly.toml`)

```toml
[[services]]
name = "marketing-landing"
type = "static"
routes = ["hostly.dev", "www.hostly.dev"]
build_command = "npm run build"
publish_directory = "dist"
```
