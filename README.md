<div align="center">

# Atelier — deploy template

**One-click hosting for a site you built with [Atelier](https://aincient-labs.com).**

Export your site with `drush aex`, drop it in, and push — this repo deploys it to Netlify,
Cloudflare Pages, Vercel, or GitHub Pages, no build step required.

</div>

---

## How it works

Atelier's [static export](https://aincient-labs.com/docs/static-export) (`drush aex`) produces a folder
of plain HTML/CSS/assets. This repo is a ready-made home for it: the static files live in **`site/`**, and
every host below is pre-configured to publish that folder as-is.

## Use it

1. **Get your own copy.** Click **“Use this template” → Create a new repository** at the top of this repo
   (or clone it).
2. **Add your export.** Build it against your final domain, then replace the contents of `site/` with it:
   ```bash
   drush aex --base-url https://your-domain.com --out /path/to/your-repo/site
   ```
   (Or run `drush aex` and copy the `aincient-export/` files into `site/`.) Keep the `.nojekyll` file.
3. **Deploy.** Push to your repo and connect a host below — or use a one-click button.

## One-click deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/aincient-labs/atelier-deploy-template)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/aincient-labs/atelier-deploy-template)

> The buttons deploy this template as-is (you'll see the placeholder page). After it's connected, push your
> export to `site/` and the host redeploys automatically.

## Per-host notes

| Host | Publish dir | How |
| --- | --- | --- |
| **Netlify** | `site` | Button above, or connect your repo — [`netlify.toml`](netlify.toml) sets the publish dir. No build command. |
| **Vercel** | `site` | Button above, or import the repo (framework preset **Other**) — [`vercel.json`](vercel.json) sets the output dir. |
| **Cloudflare Pages** | `site` | Connect your repo in **Workers & Pages**, leave the build command empty, set output dir to `site`. Or `wrangler pages deploy site` ([`wrangler.toml`](wrangler.toml)). |
| **GitHub Pages** | `site` | Enable **Settings → Pages → Source: GitHub Actions**. The included [workflow](.github/workflows/pages.yml) publishes `site/` on every push to `main`. |

## Updating

Re-run `drush aex`, refresh the files in `site/`, and push. Every host above redeploys on push.

## Full guide

Step-by-step for each host, including custom domains and `--base-url`:
**[aincient-labs.com/docs/deploy](https://aincient-labs.com/docs/deploy)**.

---

<div align="center">

Built for [Atelier by AIncient Labs](https://aincient-labs.com) · [Docs](https://aincient-labs.com/docs) · [Atelier repo](https://github.com/aincient-labs/atelier)

</div>
