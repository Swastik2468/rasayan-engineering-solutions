# Rasayan Engineering Solutions — Website

Marketing site for Rasayan Engineering Solutions, a chemical and process
engineering consultancy based in Vadodara.

Single-page, static, no build step. Everything lives in one file.

## Structure

```
index.html        Entire site — markup, inline <style>, inline <script>
logo.png          Full company logo (emblem + wordmark)      [feature/company-logo]
logo-mark.png     Circular emblem, used in navbar + footer    [feature/company-logo]
.gitattributes
```

Sections in `index.html`: hero, about, services, expertise, industries,
why-us, how-we-work, CTA, contact, footer. Navigation is in-page anchor
links.

## Tech

- Hand-written HTML + CSS. No framework, no bundler, no dependencies.
- CSS design tokens (colours, fonts, spacing) in the `:root` block at the
  top of the `<style>` — edit there to re-theme.
- Fonts loaded from Google Fonts (Manrope, Inter, JetBrains Mono) — the
  only external request.
- Vanilla JS: sticky-navbar state, mobile menu toggle, scroll-reveal
  (`IntersectionObserver`), contact-form validation.

## Run locally

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Or just open `index.html` in a browser
(fonts still load from the CDN).

## Deploy

Static — publish `index.html` (and the `logo*.png` files) to any static
host: GitHub Pages, Netlify, Cloudflare Pages, S3, nginx. No server-side
runtime.

## Editing content

Company details (name, tagline, contact info) appear directly in the
`index.html` markup. A `COMPANY_INFO` object exists in the `<script>` but
is not yet wired to the DOM.

## Open work

Tracked in [GitHub issues](https://github.com/Swastik2468/rasayan-engineering-solutions/issues):

- **#1** Company logo — added to navbar + footer on `feature/company-logo`.
- **#2** Contact form has no backend. It validates and clears on submit
  but does not send anything. Needs a mail service (Formspree / Web3Forms)
  or a `mailto:` fallback.
