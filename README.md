# Simama FC ⚽

A football club for kids who once slept on Kigali's streets — with a mission to build a team in every district in Rwanda.

This is the club's website: a single, self-contained `index.html` (HTML + CSS + JS, no build step). It works the moment you open it.

**Stand up. Play on.**

---

## Quick start

Just open `index.html` in any browser. That's it — everything's in one file.

---

## Host it on GitHub Pages (free)

1. **Create a repo** on GitHub, e.g. `simama-fc`.
2. **Upload these files** (`index.html`, `.nojekyll`, `.gitignore`, `README.md`) — drag them into the repo's *Add file → Upload files*, or push from the command line:
   ```bash
   git init
   git add .
   git commit -m "Simama FC website"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/simama-fc.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Pick branch **`main`**, folder **`/ (root)`**, and click **Save**.
6. Wait ~1 minute. Your site goes live at:
   ```
   https://YOUR-USERNAME.github.io/simama-fc/
   ```

> The `.nojekyll` file is already included so GitHub serves the site as-is.

### Custom domain (optional)
If you have a domain (e.g. `simamafc.org`): add a file named `CNAME` containing just your domain, then set the DNS records GitHub shows you under **Settings → Pages → Custom domain**.

---

## Edit the content

Open `index.html` and scroll to the `<script>` near the bottom. Everything is in plain arrays:

| What | Where |
|------|-------|
| Players (name, number, position) | `PLAYERS` |
| News / updates feed | `NEWS` |
| Photo gallery tiles | `GALLERY` |
| Fundraising goal + amount raised | `GOAL` and `RAISED` |

### Swap the demo photos for real ones
The colored tiles are placeholders. Search the file for `data-swap` — each one marks a spot where you replace the placeholder `<div class="ph">…</div>` with a real image:
```html
<img src="photos/team.jpg" alt="Simama FC squad">
```
Put your images in a `photos/` folder in the repo and reference them by path.

---

## Make it fully live

Right now news, gallery and donations are front-end only. To let the team post updates and take real donations without editing code:

1. **News + gallery uploads** — use [Supabase](https://supabase.com): a table for news, a storage bucket for photos, and an admin page to post. Replace the `NEWS` / `GALLERY` arrays with a `fetch` on page load.
2. **Real donations** — in Rwanda, [IremboPay](https://irembopay.com) or [Flutterwave](https://flutterwave.com) handle MTN/Airtel Mobile Money and cards; [Stripe](https://stripe.com) is good for international/diaspora donors. Search the file for `>>> GO LIVE` — the two spots to wire are marked.
3. **Contact form** — point it at Supabase, or [Formspree](https://formspree.io) for zero backend.

---

## Tech
Plain HTML/CSS/JS. Fonts: Anton, Manrope, Space Mono (loaded from Google Fonts). No frameworks, no dependencies.

© Simama FC · Kigali, Rwanda
