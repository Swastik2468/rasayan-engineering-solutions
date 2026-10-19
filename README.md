# Rasayan Engineering Solutions — Website

Marketing site for Rasayan Engineering Solutions, a chemical and process
engineering consultancy based in Vadodara.

Single-page, static, no build step. Everything lives in one file.

**Live:** <https://swastik2468.github.io/rasayan-engineering-solutions/>
(GitHub Pages, deployed from `main`).

**Content/company reference:** [Rasayan Engineering Solutions – Company
Brain](https://claude.ai/artifact/7djnjCMyJf196g8tYNFfGm#c7752bf0-3d55) —
brand, services, positioning, and the real company details (background,
founder, headcount) that `index.html`'s placeholder fields
(`[Company Background]` etc.) still need to be filled in from. See
`TASKS.md`.

## Structure

```
index.html        Entire site — markup, inline <style>, inline <script>
assets/
  logo_rasayan_engg.png   Company logo (emblem + wordmark); navbar, footer, favicon
.gitattributes
```

Sections in `index.html`: hero, about, services, projects, expertise, industries,
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

Live on **GitHub Pages**, served straight from `main` —
<https://swastik2468.github.io/rasayan-engineering-solutions/>. No build
step, no CI: whatever's on `main` is what's live. Static, so it'd also run
unchanged on Netlify, Cloudflare Pages, S3, or nginx if that ever changes.

## Editing content

Company details (name, tagline, contact info) appear directly in the
`index.html` markup. A `COMPANY_INFO` object exists in the `<script>` but
is not yet wired to the DOM.

## Open work

Tracked in [GitHub issues](https://github.com/Swastik2468/rasayan-engineering-solutions/issues):

- **#3** Logo — added to navbar, footer, favicon (`assets/logo_rasayan_engg.png`). #1 is a duplicate.
- **#2** Contact form has no backend. It validates and clears on submit
  but does not send anything. Needs a mail service (Formspree / Web3Forms)
  or a `mailto:` fallback.
