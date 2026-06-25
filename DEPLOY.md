# 🚀 Deploying Sparkle Unicorn Magic Garden

The whole game is one self-contained file: **`index.html`**. No build step, no server code.
To put it online you just need to (1) host that file and (2) point a domain at it.

---

## Option A — Netlify (easiest, free, custom domain + HTTPS)

1. Go to <https://app.netlify.com> and sign up (free).
2. Click **Add new site → Deploy manually**.
3. Drag this whole folder onto the upload area.
   - It goes live instantly at a `something-random.netlify.app` address.
4. Add your domain: **Site settings → Domain management → Add a domain**.
5. Follow Netlify's DNS instructions at your registrar. HTTPS turns on automatically.

To update the game later, just drag the folder in again (or connect the GitHub repo for auto-deploys).

---

## Option B — Cloudflare Pages (free, fast, great if you buy the domain at Cloudflare)

1. Buy the domain at <https://dash.cloudflare.com> (Domains).
2. **Workers & Pages → Create → Pages → Upload assets**, upload `index.html`.
3. **Custom domains → Set up a domain** → pick your domain. Done — DNS + HTTPS are automatic.

---

## Option C — GitHub Pages (free, version-controlled)

1. Create a repo on GitHub and push this folder:
   ```bash
   git add index.html .gitignore DEPLOY.md
   git commit -m "Sparkle Unicorn Magic Garden"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
2. Repo **Settings → Pages → Source: Deploy from a branch → main / root**.
3. It publishes at `https://<you>.github.io/<repo>/`.
4. For a custom domain: **Settings → Pages → Custom domain**, then add a `CNAME`
   DNS record at your registrar pointing to `<you>.github.io`.

---

## Buying the domain

Any registrar works — Cloudflare (cheapest, at-cost), Namecheap, or Porkbun are all good (~$10–15/yr).
After buying, follow the DNS steps from whichever host above you chose.

## Notes
- `index.html` must keep that exact name — hosts serve it automatically as the homepage.
- It uses Google Fonts over the internet but falls back to a system font if offline.
- `node_modules/` and `package*.json` are only for local browser testing and are git-ignored —
  they are **not** needed to run or host the game.
