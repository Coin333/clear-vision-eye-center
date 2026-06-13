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

## Deploy

Static site, drop it anywhere: Vercel, Netlify, GitHub Pages, or any host. No build step.

Built with D1 Vibe Coding
