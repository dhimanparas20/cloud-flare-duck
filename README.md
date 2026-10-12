# 🦆 It All Ends Here

A single-page, dark-themed joke website. One duck walks forever, one button runs
away, and a very serious headline insists that **"It all ends here."**

Plain HTML, CSS, and vanilla JS. Bootstrap and Tailwind load from a CDN, so there
is no build step and no dependencies. The whole site is one file: `index.html`.

## 📁 Files

```
site/
├── index.html   # the whole site (styles and scripts are inline)
└── README.md
```

## 🚀 Deploy to Vercel

Vercel serves a static `index.html` as-is. No framework, build command, or config
file is needed.

### Option 1: Vercel dashboard (Git)

1. Push this folder to a GitHub repository:

   ```bash
   git add .
   git commit -m "Duck site"
   git push origin main
   ```

2. Go to [vercel.com/new](https://vercel.com/new) and import the repository.
3. Use these settings:
   - **Framework Preset:** `Other`
   - **Build Command:** (leave empty)
   - **Output Directory:** (leave empty, or `.`)
4. Click **Deploy**.

Your site is live at `https://<project>.vercel.app`.

### Option 2: Vercel CLI (no GitHub needed)

```bash
cd site
npx vercel --prod
```

Log in when prompted, accept the defaults, and the CLI prints the live URL.

## 🛠 Troubleshooting

- **Blank page or unstyled text:** Bootstrap, Tailwind, and the fonts load from
  CDNs, so the browser needs internet access.
- **Wrong page shown:** The file must be named exactly `index.html` in the
  deployed folder (Windows can hide `.html` extensions and save `index.html.html`).

## 📄 License

MIT. The ducks won't mind.
