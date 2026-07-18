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

[![Use this template](https://img.shields.io/badge/Use%20this%20template-2ea44f?style=for-the-badge&logo=github&logoColor=white)](https://github.com/aincient-labs/atelier-deploy-template/generate)

1. **Get your own copy.** Click **“Use this template” → Create a new repository** above (or the badge), or
   clone it.
2. **Add your export.** Build it against your final domain, then replace the contents of `site/` with it:
   ```bash
   drush aex --base-url https://your-domain.com --out /path/to/your-repo/site
   ```
   (Or run `drush aex` and copy the `aincient-export/` files into `site/`.) Keep the `.nojekyll` file.
3. **Deploy.** Push to your repo and connect a host below — or use a one-click button.

## One-click deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/aincient-labs/atelier-deploy-template)
[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/aincient-labs/atelier-deploy-template)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/aincient-labs/atelier-deploy-template)

> These buttons deploy the template as-is — you'll first see the placeholder page. Once the host is connected,
> push your own export to `site/` and it redeploys automatically. For **GitHub Pages**, use the **“Use this
> template”** badge above instead, then enable Pages once (see the table below).

## Per-host notes

This repo ships the config each host needs (publish dir = `site`); the **Docs** column links each host's
own official guide — always the source of truth if a UI changes.

| Host | This repo provides | Official docs |
| --- | --- | --- |
| **Netlify** | [`netlify.toml`](netlify.toml) sets the publish dir; no build command | [Deploy](https://docs.netlify.com/site-deploys/create-deploys/) · [CLI](https://docs.netlify.com/cli/get-started/) |
| **Vercel** | [`vercel.json`](vercel.json) sets the output dir (framework preset **Other**) | [Git deploys](https://vercel.com/docs/deployments/git) · [CLI](https://vercel.com/docs/cli) |
| **Cloudflare Pages** | [`wrangler.toml`](wrangler.toml) (`wrangler pages deploy site`) — or connect your repo, output dir `site` | [Git integration](https://developers.cloudflare.com/pages/get-started/git-integration/) · [Direct upload](https://developers.cloudflare.com/pages/get-started/direct-upload/) |
| **GitHub Pages** | [workflow](.github/workflows/pages.yml) publishes `site/` on push to `main` | [Custom Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages) |

> **GitHub Pages — one-time setup:** enable it once at **Settings → Pages → Source: GitHub Actions**
> ([docs](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)).
> Netlify, Cloudflare, and Vercel need no equivalent toggle.

## Updating

Re-run `drush aex`, refresh the files in `site/`, and push. Every host above redeploys on push.

## Full guide

Step-by-step for each host, including custom domains and `--base-url`:
**[aincient-labs.com/docs/deploy](https://aincient-labs.com/docs/deploy)**.

---

<div align="center">

Built for [Atelier by AIncient Labs](https://aincient-labs.com) · [Docs](https://aincient-labs.com/docs) · [Atelier repo](https://github.com/aincient-labs/atelier)

</div>
