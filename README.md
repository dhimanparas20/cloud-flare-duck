# 🦆 It All Ends Here

A single-page, dark-themed joke website. One duck walks forever, one button runs
away, and a very serious headline insists that **"It all ends here."**

Made with plain HTML, CSS, and vanilla JS. Bootstrap + Tailwind load from a CDN,
so there are no build steps and no local dependencies — just one file.

## 📁 Files

```
site/
└── index.html      # the whole site (styles + scripts are inline)
```

## 🚀 Deploy to Cloudflare Pages

There are three ways. **Git integration is the most reliable.**

### 1. Git integration (recommended)

1. Push this folder to a GitHub or GitLab repository:

   ```bash
   git init
   git add index.html
   git commit -m "Static duck site"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```

2. Cloudflare dashboard → **Workers & Pages → Create application**.
3. Choose **Pages → Connect to Git**, authorise and select your repo.
4. Build settings:
   - **Branch:** `main`
   - **Build command:** (leave empty)
   - **Output directory:** `/`
5. **Save and Deploy**.

Your site goes live at `https://<project>.pages.dev`.

### 2. Direct upload (drag & drop)

1. **Workers & Pages → Create application → Pages → Upload assets**.
2. Drag the **`site` folder** (or a zip of it) into the drop zone — not a stray file.
3. **Deploy site**.

### 3. Wrangler CLI

```bash
npx wrangler login
npx wrangler pages deploy site
```

## 🛠 Troubleshooting

- **`Error 1101 — Worker threw exception` on a static site.** This is *not* caused
  by the HTML. A static deployment returning 1101 means Cloudflare is routing the
  request through a Worker/function that is crashing. Things to try:
  1. Make sure no `_worker.js`, `worker.js`, or `functions/` folder is in the repo.
  2. Project → **Settings → Builds & deployments → Build system version** — try
     switching between **Version 1** and **Version 2** and redeploy.
  3. Deploy with `npx wrangler pages deploy site` (CLI path often sidesteps the
     dashboard build-system bug).
  4. Check the [Cloudflare Status](https://www.cloudflarestatus.com) page, or report
     it in the Cloudflare Workers Discord (`#pages-general`).

- **Blank page / missing CSS?** Everything (Bootstrap, Tailwind, fonts) loads from
  CDNs, so the site needs internet access to render styles.

## 📄 License

MIT — do whatever you want with it. The ducks won't mind.