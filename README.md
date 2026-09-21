# Santhica — website

The marketing website for **Santhica**, applied AI for healthcare. Tagline: *Care that connects.*

Santhica turns what already happens in a consultation — a spoken conversation, a handwritten prescription, a lab report — into a structured, FHIR-aligned patient record that stays useful across visits. The product is mobile-first and offline-capable, built for clinics, nursing homes and hospitals in India. The site presents three layers: **Voice Scribe** (speech to structured record), **longitudinal patient context** (one continuous history), and **clinical agents** that act on that context.

## What the site covers

### Product

| Page | Covers |
| --- | --- |
| `index.html` | The full story end to end: Voice Scribe, longitudinal context, the agents, the clinical safety net, outpatient and inpatient previews, offline-first mobile, and app download links. |
| `platform.html` | Healthcare AI OS overview — how the layers fit together. |
| `voice-scribe.html` | Consultations in English, Hindi and Bengali becoming discrete clinical fields for clinician review. |
| `agents.html` | The three agents — Clinical Intelligence, Documentation, Care Closure — plus the safety-net checks and an illustrative OPD capacity model. |
| `clinical-workflows.html` | Outpatient and inpatient pathways, treatment charts and hand-offs. |
| `strategy.html` | Approach to practical healthcare AI. Placeholder; content pending. |

### Company

`about.html` (purpose and team) · `careers.html` (placeholder) · `contact.html` (demo request; composes an email draft locally, no backend)

### Writing

`blogs.html` lists three articles: what longitudinal patient context is, how a paper prescription can start a connected record, and carrying context from outpatient visit into inpatient care.

### Legal and credits

`privacy-policy.html` · `terms-of-service.html` · `media-credits.html` (stock footage attribution)

## What is and isn't real

This matters, because the site shows clinical-looking data throughout.

- **Every patient, value and prescription is fictional.** John Doe, the potassium and Hb results, the amoxicillin and warfarin examples — all invented sample data. No real patient information appears anywhere.
- **Product mockups are HTML and CSS**, not screenshots of the running app.
- **Care Closure and agent-assisted coordination are labelled in development** or as workflow concepts, not shipped features.
- **The 13,000-hour figure is an explicit model**, not a measured result: 500 visits × 26 days × 12 months × 5 assumed minutes ÷ 60.
- **ABDM certification is on the roadmap**, not held.
- **Background clips are licensed stock footage.** The people and facilities shown are not Santhica customers or staff. See [assets/video/LICENSES.md](assets/video/LICENSES.md).

## Status

Published as a **preview** through GitHub Pages. Every page carries `noindex, nofollow, noarchive` and `robots.txt` disallows crawling, so it stays out of search results.

> Both of those have to be removed before this becomes the production site, or the real site will never be indexed.

## Running it

Static HTML, CSS and JavaScript. No build step, no dependencies.

```sh
python3 -m http.server 4173 --bind 127.0.0.1
```

Then open <http://127.0.0.1:4173/>. Opening `index.html` directly works too, though browser restrictions may block clipboard copying on `file://` URLs.

Stylesheets load in order, each layer overriding the last: `site.css` (foundations) → `landing.css` (homepage, light-theme tokens) → `blog.css` / `legal.css` → `components.css` (product cards, agents, safety net, device mockups).

Motion throughout is opt-in behind `prefers-reduced-motion: no-preference`; reduced-motion visitors get the finished static state.

`.nojekyll` is deliberate — it tells GitHub Pages to serve the tree verbatim instead of running Jekyll over it. Keep it.
