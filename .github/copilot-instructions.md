## Purpose
This repository is a small static website (plain HTML + inline CSS) in Brazilian Portuguese. These instructions help AI agents make safe, focused edits that follow existing project patterns.

## Big picture (what to know first)
- Single-page-per-file site: main pages are `index.html`, `construcao-historia.html`, and `construcao-orcamento.html`.
- No build system or server-side code: files are served as static HTML (open locally or deploy to GitHub Pages).
- Styling is inline in each HTML file but uses a shared visual language: CSS variables (e.g. `--dourado-luxo`, `--cinza-concreto`) are repeated across pages — keep them consistent when changing theme.

## Key files to inspect
- [index.html](index.html) — entry page with hero, services, and navigation.
- [construcao-orcamento.html](construcao-orcamento.html) — budget request form (external integration).
- [construcao-historia.html](construcao-historia.html) — company history and timeline.

## Project-specific patterns and conventions
- Language & encoding: every page uses `lang="pt-BR"` and `UTF-8`. Preserve both.
- Navigation is duplicated in each page (static links like `index.html`, `construcao-historia.html`). When changing the nav, update all pages.
- Design tokens: color and font variables are declared in `:root` inside each file — treat them as the single source of truth for that page. Prefer minimal edits: change variables rather than many selectors when adjusting theme.
- Typography: Google Fonts (`Oswald`, `Montserrat`) are loaded from `fonts.googleapis.com`. Keep the same family names for visual consistency.

## External integrations and gotchas
- Form submission: the contact form posts to FormSubmit (action="https://formsubmit.co/gabriel.comparini.ismart@gmail.com"). Do not replace this endpoint without confirming the new destination.
- No JavaScript bundles or node/npm dependencies present — adding complex JS should include clear rationale and an explicit plan for bundling or progressive enhancement.

## Developer workflow notes
- Preview: there is no build step — open files directly in a browser or use a Live Server extension for hot-reload.
- Testing: no automated tests detected. Validate visual changes locally across multiple viewports (`@media` rules exist for responsiveness).
- Committing: edits are simple HTML/CSS changes. Keep commits small and reference which pages were updated (e.g., "Atualiza navegação em index, história e orçamento").

## Examples from this repo
- Nav links example (update all pages if changed): `<li><a href="construcao-orcamento.html">Solicitar Proposta</a></li>`
- Form example (preserve hidden inputs): `<form action="https://formsubmit.co/gabriel.comparini.ismart@gmail.com" method="POST">` with `_subject`, `_captcha`, `_template` hidden fields.

## When to ask the human
- If you need to change the form email, or replace FormSubmit with another backend, ask for the new endpoint and confirmation.
- If proposing to extract shared CSS into a single stylesheet or add build tooling, present a short migration plan and list of files to modify.

## Minimal constraints for edits
- Preserve `lang="pt-BR"` and `charset="UTF-8"`.
- Keep visible text in Portuguese unless instructed otherwise.
- Update navigation links consistently across all pages.

If anything here is unclear or you'd like me to add examples (e.g., a small migration plan to extract common CSS), tell me which area to expand.
