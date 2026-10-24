# Custom Domains & Automated SSL

Attach custom apex domains (`example.com`) or subdomains (`app.example.com`) to any Hostly web service.

---

## Steps to Configure
1. In your Hostly project console, go to **Settings $\rightarrow$ Domains**.
2. Add your custom domain (e.g. `api.example.com`).
3. Add the provided `CNAME` record to your DNS provider (Cloudflare, GoDaddy, Namecheap):
   ```
   Type: CNAME
   Name: api
   Target: cname.hostly.dev
   ```
4. Hostly automatically verifies DNS propagation, generates a Let's Encrypt SSL certificate, and activates HTTPS routing within seconds.

---

## Apex Domain Support
For root domains (`example.com`), Hostly provides Anycast `A` records or ALIAS/ANAME record targets:
```
Type: A
Name: @
Target: 76.76.21.21
```
