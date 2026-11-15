# fadyrezkghattas.github.io

Personal research site. Jekyll + Minimal Mistakes, deployed to GitHub Pages by
`.github/workflows/jekyll.yml` on push to `master`.

## Where things live
- All home-page content is data: `_data/profile.yml` (hero: name, role, status line,
  links, interest tags), `research.yml`, `news.yml`, `publications.yml`,
  `experience.yml`, `education.yml`. Content updates should be YAML-only.
- `index.html` holds the About text and the section markup; `_pages/publications.html`
  renders all of `publications.yml` (`selected: true` controls the home page).
- Minimal Mistakes is vendored. Do not edit `_sass/minimal-mistakes/`. Restyle via the
  variables at the top of `assets/css/main.scss` and the rules in `_sass/_site.scss`.
- Pages use `_layouts/plain.html`; partials are `_includes/profile-header.html`,
  `publication.html`, `experience-entry.html`.
- The CV PDF at `assets/files/Fady_Rezk_CV.pdf` is the source of truth for facts.

## Content rules
- Never invent facts (dates, venues, links, co-authors). If something is missing,
  leave a `TODO` (YAML comment or `<!-- TODO -->`).
- Text supplied by the owner goes in verbatim. Items marked [VERIFY] go in as written
  with an `<!-- VERIFY -->` comment next to them.
- "Fady Rezk" is bolded automatically in author lists; don't hard-code `<strong>`.

## Build and deploy
- CI: Ubuntu 22.04, Ruby 3.1, `bundle exec jekyll build --baseurl <from configure-pages>`.
  Local-build workarounds never go into `_config.yml` or the workflow.
- New root-level `.md` files without front matter get published as static files; add
  them to `exclude` in `_config.yml` if they are not site content.
