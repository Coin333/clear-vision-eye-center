# Clear Vision Eye Center

Marketing website for Clear Vision Eye Center of Pomona, CA, the practice of board-certified ophthalmologist Dennis A. Chuck, M.D.

A static, build-free site (HTML + Tailwind CDN + Lucide icons). Warm "bone" and ink-navy editorial theme with a blue medical accent, scroll-aware navigation, reveal animations, patient education on cataracts, a trilingual toggle (English / Spanish / Chinese), and a working appointment request form (delivered via FormSubmit, no backend required).

## Run it

Just open the file:

```bash
open index.html
```

Or serve locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Pages

- `index.html` — home: hero eye-chart, stats, services, conditions, cataract before/after slider, doctor bio, team band, reviews strip, FAQ, contact form
- `services.html` — in-depth service content (cataract surgery + lens options, comprehensive eye exams, optical shop, lens implants, glaucoma) with a sticky table of contents
- `reviews.html` — filterable wall of real Google patient reviews, rating summary, featured quotes
- `staff.html` — team page driven by a Google Sheet (see `STAFF-PAGE-GUIDE.md`); ships with a built-in roster so it's never empty
- `privacy.html` — privacy policy, including FormSubmit third-party disclosure
- `accessibility.html` — WCAG 2.1 AA accessibility statement

## Notable features

- Trilingual toggle (EN / ES / 中文) that translates text nodes by dictionary, preserving icons and layout
- Live open / closed hours badge with an editable holiday-closure list
- LocalBusiness / Physician JSON-LD structured data for search engines
- Google-Sheet-backed staff page that the office updates with no code

## Practice details

- 1774 Alameda St, Pomona, CA 91768
- (909) 622-1188
- ask.doctorchuck@gmail.com
- Mon–Fri 8:00 AM – 5:00 PM (lunch 12:30–1:30), Saturday by request

## Deploy (Cloudflare Pages)

This is a static site with no build step, so deployment is just "serve these files."

### Option A — connect the GitHub repo (recommended)

1. In the Cloudflare dashboard go to **Workers & Pages → Create → Pages → Connect to Git**.
2. Pick this repository (`Coin333/clear-vision-eye-center`) and the `main` branch.
3. Build settings:
   - **Framework preset:** `None`
   - **Build command:** _(leave empty)_
   - **Build output directory:** `/`
4. Click **Save and Deploy**. Every push to `main` then auto-deploys.

### Option B — direct upload via Wrangler

```bash
npx wrangler pages deploy . --project-name=clear-vision-eye-center
```

### Custom domain

After the first deploy, in the Pages project go to **Custom domains → Set up a domain** and add `pomonaeyedoctor.com` (and `www`). Cloudflare provisions HTTPS automatically. The canonical URLs, sitemap, and structured data already point to `https://www.pomonaeyedoctor.com/`.

### Production files in this repo

- `_headers` — security headers + long-cache for `/assets/*` (Cloudflare Pages reads this automatically)
- `robots.txt` and `sitemap.xml`
- `404.html` — branded not-found page (Cloudflare Pages serves it for unmatched routes)

### Before going live

- Activate the contact form: submit the form once and click the confirmation email FormSubmit sends to `ask.doctorchuck@gmail.com`.
- Fill in the staff Google Sheet (see `STAFF-PAGE-GUIDE.md`); the page reads it live.

Built with D1 Vibe Coding
