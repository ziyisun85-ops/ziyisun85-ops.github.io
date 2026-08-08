# AGENTS.md

## Cursor Cloud specific instructions

This repo is a **Jekyll static site** (the "Minimal Light" theme used as a personal
homepage). The site content lives in `index.md` + `_includes/*.md`, config in
`_config.yml`, and layout/styles in `_layouts/` and `_sass/`.

### Environment
- Ruby 3.2 and `bundler` are preinstalled in the VM image; gems are installed by the
  update script into `$HOME/.jekyll-bundle` (configured via `.bundle/config`, which is
  outside the source tree so Jekyll doesn't try to process `vendor/`).
- Do not commit `.bundle/config` — it holds a machine-specific absolute gem path and is
  recreated by the update script.

### Run / build / serve (dev)
- Serve locally: `bundle exec jekyll serve --host 0.0.0.0 --port 4000 --no-watch`
  then open `http://localhost:4000/`.
- One-off build: `bundle exec jekyll build` (output in `_site/`).
- There is no separate lint or automated test suite; `jekyll build` succeeding (no
  errors) is the effective correctness check for content/config changes.

### Non-obvious gotchas
- `--no-watch` is required. With auto-regeneration (the default for `jekyll serve`),
  Jekyll 3.8.x + Ruby 3.2 crashes in `pathutil` 0.16.2 (`no implicit conversion of Hash
  into Integer` while reading `/proc/version`). A plain `jekyll build` is unaffected, so
  after editing content, rebuild/restart manually instead of relying on live reload.
- `rexml` is declared in the `Gemfile` because it was removed from Ruby's default gems in
  Ruby 3.x but is still required by `kramdown` 1.x (mirrors why the README also adds
  `webrick`).
- `_config.yml` defines a custom `exclude:` list, which replaces Jekyll's default
  excludes. Keep bundled gems out of the source tree (the update script installs them to
  `$HOME/.jekyll-bundle`) so Jekyll doesn't try to render gem-internal templates.
- The `Logger not initialized properly` / `Stevenson#initialize` warnings on startup are
  harmless Ruby 3.2 vs. old-Jekyll noise, not errors.
