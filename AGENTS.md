# Repository Guidelines

## Project Structure & Module Organization
- `_posts/` blog posts (`YYYY-MM-DD-title.md`).
- `_layouts/`, `_includes/`, `_sass/` theme templates and styles.
- `_javascript/` source JS bundled via Rollup to `assets/js/dist`.
- `assets/` static files (images, css, js, libs).
- `_config.yml` site settings; `_data/` locales and data; `_tabs/` standalone pages.
- `tools/` helper scripts (`run`, `test`); `docs/` project meta.

## Build, Test, and Development Commands
- Install deps: `bundle install` (Ruby) and `npm install` (Node dev tools).
- Run locally: `bash tools/run` or `bundle exec jekyll s -H 0.0.0.0 -l`.
- Production build: `JEKYLL_ENV=production bundle exec jekyll b`.
- JS assets: `npm run watch` (dev) or `npm run build` (prod Rollup bundling).
- SCSS lint: `npm test` (stylelint) or `npm run fixlint` to auto-fix.
- Site test: `bash tools/test [-c "_config.yml,_config.dev.yml"]` (html-proofer, internal links only).

## Coding Style & Naming Conventions
- Editor config: 2 spaces, LF, UTF-8; final newline; trim trailing whitespace (except `.md`).
- Quotes: JS/CSS/SCSS single; YAML double. Prettier `trailingComma: none`.
- SCSS follows `stylelint-config-standard-scss` (see `package.json`).
- Posts: name `YYYY-MM-DD-my-post.md`; front matter includes at minimum:
  ```yaml
  ---
  layout: post
  title: My Post
  categories: [category]
  tags: [tag]
  ---
  ```
- Place images under `assets/img/...`; reference with `/assets/img/...`.

## Testing Guidelines
- Use `bash tools/test` to build and run html-proofer.
- Fix broken internal links, missing images, and invalid anchors before opening a PR.
- No coverage requirement; keep pages accessible and warnings-free.

## Commit & Pull Request Guidelines
- Conventional Commits enforced by commitlint/husky.
  - Examples: `feat(posts): add Java guide`, `fix(css): correct header z-index`, `docs: update README`.
- PRs include: concise description, linked issues (e.g., `Closes #123`), relevant screenshots for UI, and a note that local build/tests passed.

## Security & Configuration Tips
- Do not commit secrets. Configure analytics/comments in `_config.yml` (`google_analytics.id`, `comments.*`).
- Respect PWA and asset settings (`assets.self_host`, `pwa.cache`). Test in production mode when changing them.

## Agent-Specific Notes
- Keep changes minimal and scoped; follow existing structure and styles.
- Prefer updating theme sources (`_sass/`, `_javascript/`) and rebuilding assets rather than editing generated files.
