# Create A Dot — Website Package

This package contains the full demo website for Create A Dot, built as static HTML/CSS/JS. No build step, framework, or server is required — it runs in any browser.

## What's included

```
create-a-dot-website/
├── index.html              Home page
├── about.html               About page
├── services.html            Services page (all 7 services)
├── projects.html             Projects / portfolio page
├── pricing.html               Pricing page
├── contact.html                Contact page
├── quick-preview.html          Single-file version of the whole site (all pages in one file, for fast sharing/preview)
├── css/
│   └── style.css              Shared stylesheet (design tokens, layout, components)
├── js/
│   └── main.js                Shared behavior (nav, dark mode, scroll reveal, FAQ, filters, forms)
└── img/                        Empty folder — drop real photography/logos here
```

## How to view it

**Option A — just open it**
Double-click `index.html` (or any page) to open it directly in your browser. All pages link to each other correctly since they sit in the same folder.

**Option B — local server (recommended for development)**
Some browsers restrict certain features when opening files directly (`file://`). To avoid that, serve the folder locally:

```bash
cd create-a-dot-website
python3 -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.

**Option C — quick share**
`quick-preview.html` is a single self-contained file (no external css/js files needed) — useful for emailing or dropping into a chat/Slack for a fast look at the whole site.

## Design system

- **Colors:** Ink `#0F172A`, Blue `#2563EB`, Cyan `#22D3EE`, Background `#FFFFFF`, Text `#111827` — all defined as CSS variables at the top of `style.css`, so re-theming means editing a handful of values.
- **Typography:** Manrope (headings/body), JetBrains Mono (labels, stats, tags) — loaded from Google Fonts via `<link>` tags in each page's `<head>`.
- **Dark mode:** toggled via a `.dark` class on `<html>`, persisted in `localStorage`.
- **Signature motif:** the "dot path" — a single dot growing into an ascending connected line — appears in the hero graphic, the "Our Process" sections, and the logo mark, tying back to the "From One Dot to Digital Success" tagline.

## Before going live

This is a design/demo build. Before launch:

1. Replace placeholder copy (testimonials, project results, phone/WhatsApp numbers, email) with real details.
2. Replace inline SVG illustrations with real photography, screenshots, or client logos.
3. Wire the contact form and newsletter form to a real backend or form service (Formspree, Netlify Forms, a WordPress REST endpoint, etc.) — they currently just show a "sent" confirmation client-side.
4. Swap the Google Map placeholder for a real embedded map (Google Maps embed iframe).
5. If converting to WordPress: the `services.html` service blocks and `pricing.html` cards map cleanly to repeatable ACF/Gutenberg blocks; `css/style.css` can be enqueued as-is or split into a theme's `style.css`.

## Tech stack used

Plain HTML5, CSS3 (custom properties, `color-mix()`, CSS Grid/Flexbox), vanilla JavaScript (no framework, no build tools). Fonts via Google Fonts CDN.
