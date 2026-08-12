# santhica.com — website design preview

A design proposal for santhica.com, published for internal review.

**This is not the production website.** The live site is unaffected and continues to
be served from its own repository. Nothing here is deployed to `santhica.com`, and this
repository deliberately contains no `CNAME` file, so it cannot claim that domain.

**Live preview:** see the GitHub Pages URL in the repository description.

---

## Why this exists

The current site is a single hero, an about section and a contact form. It reads as a
company that has not shipped a product. Santhica has shipped one — handwriting
extraction, in-patient treatment charts, voice consultation, a clinical safety net, a
longitudinal patient record, offline-first sync and ABDM-aligned identity — and almost
none of that is visible to a visitor.

This preview restructures the site around what the product actually does, and shows the
product rather than describing it.

## What to review

- **Structure** — section order and the story it tells
- **Visual direction** — typography, colour, density, the animated app screens
- **Copy** — headline positioning in particular

Copy and imagery are still in progress. Feedback on structure and look is more useful
right now than line edits.

## Structure

```
index.html               landing page
privacy-policy.html      current legal text, restyled
terms-of-service.html    current legal text, restyled
assets/
  css/legal.css          shared styling for the legal pages
  img/                   logo mark, logo lockup, favicon
```

Static HTML and CSS. No build step, no framework, no dependencies, no tracking, and no
network requests at runtime — the page renders offline.

## Running it locally

```bash
open index.html
```

That is the whole workflow. Any change is a file edit and a browser refresh.

## Implementation notes

- **App screens are rendered, not screenshotted.** Each phone screen is CSS keyframe
  animation, cycling through the real flow — capture, extraction, review. A few
  kilobytes rather than megabytes of video, sharp at any resolution.
- **The hero background is a canvas animation** — nodes drift and link as they near each
  other. It stops rendering when scrolled out of view, caps device pixel ratio at 2, and
  paints a single static frame under `prefers-reduced-motion`.
- **No patient data.** No names, phone numbers, or health identifiers appear anywhere.
  Medications and doses are generic clinical examples. No real app screenshots are used.
- **Not indexable.** Every page carries a `noindex` meta tag and `robots.txt` disallows
  all crawlers, so a draft cannot surface in search results.

## If this direction is approved

The design ports into the existing site repository as React components — the same CSS,
scoped under a namespace to avoid collisions with the Tailwind utilities already in use
there. Roughly half a day. Hosting cost is unchanged, which is nothing: GitHub Pages on
a public repository.

This repository is disposable and should be deleted once the review is finished.
