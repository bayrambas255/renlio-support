# Renlio — Support / Legal Pages

Self-contained HTML hosting bundle for Renlio. Pure HTML+CSS, mobile-friendly, dark mode auto.

## Files

| File | Purpose | URL after hosting |
|---|---|---|
| `index.html` | Support hub (contact + FAQ + legal links) | `/` |
| `privacy.html` | Privacy Policy | `/privacy.html` |
| `terms.html` | Terms of Service | `/terms.html` |
| `_config.yml` | GitHub Pages Jekyll config


## Hosting options

### 1. GitHub Pages (recommended — free, fast)
```bash
# In the repo root:
git add support/
git commit -m "Add legal + support pages"
git push

# GitHub → Repo → Settings → Pages
# Source: Deploy from a branch
# Branch: main (or master), Folder: /support
# Save → URL: https://<user>.github.io/<repo>/  (or your CNAME)
```

### 2. Custom domain
- Add a `CNAME` file with your domain (e.g. `renlio.com`)
- DNS: CNAME record pointing to `<user>.github.io`
- HTTPS auto-enabled by GitHub after a few minutes

### 3. Netlify / Cloudflare Pages / Vercel
- Drag-drop the `support/` folder, or connect the repo
- All three auto-detect static HTML, no build step needed

## ASC integration

After hosting, set these URLs in App Store Connect:

- **Privacy Policy URL** (per locale): `https://<user>.github.io/<repo>/privacy.html`
- **License Agreement URL** (per locale): `https://<user>.github.io/<repo>/terms.html`
- **Support URL** (ASC App Information): `https://<user>.github.io/<repo>/`
- **Marketing URL** (optional): same as Support URL or your homepage

## Customization

- **FAQ items** are app-agnostic defaults — edit `index.html` to add app-specific Q&A
- **Brand color** auto-derived from `--primary-hex`/`--colors-json` (warm coral default)
- **Logo**: change the emoji in the script's `--emoji` flag (used in favicon + header)

## Re-generate

If you update the source markdown files:
```bash
python3 ~/.claude/skills/ios-privacy-manifest/scripts/generate_legal_html.py \
    --legal-dir <path-to-legal-md> \
    --colors-json <brand-colors.json> \
    --app-name "Renlio" \
    --emoji "💳" \
    --contact-email "omerbas283@gmail.com" \
    \
    --locale tr \
    --out support/tr
```

---

**Last generated:** 2026-05-16
