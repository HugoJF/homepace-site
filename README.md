# homepace-site

Static site for Homepace at https://homepace.hugo.dev.br.

| Path | Content |
|---|---|
| `/` | Landing page |
| `/privacy/` | Privacy policy linked from the Play listing |

## Deployment

[GitHub Actions](.github/workflows/deploy.yml) publishes every push to `main`. Run it manually with `workflow_dispatch` to redeploy. There is no build step; only `index.html` and `privacy/` are uploaded.

- Netlify project: `homepace` (`e0791572-953e-473a-bba4-a5f4c3318369`).
- GitHub repository secrets: `NETLIFY_AUTH_TOKEN` and `NETLIFY_SITE_ID`.
- Netlify fallback URL: https://homepace.netlify.app.
- DNS: Cloudflare CNAME `homepace.hugo.dev.br` → `homepace.netlify.app`, DNS-only and managed through the `cf` CLI. Netlify provisions and renews HTTPS certificates; Cloudflare proxying stays off. This record is outside the homelab Terraform configuration.
