# Agents

## Cursor Cloud specific instructions

### Overview

This repository is a **pre-built static site** (React/Vite SPA) deployed via GitHub Pages. It contains only the compiled production output — there is no source code, `package.json`, build system, test framework, or linter in this repo. The source is built externally and the `dist/` output is committed here.

### Running the application locally

The `index.html` references assets at `/undervisningsopplegg/assets/`, matching the GitHub Pages path prefix. To serve locally:

```bash
mkdir -p /tmp/serve-root
ln -sf /workspace /tmp/serve-root/undervisningsopplegg
python3 -m http.server 8080 --directory /tmp/serve-root
```

Then open: `http://localhost:8080/undervisningsopplegg/index.html`

### Key constraints

- **No lint, test, or build commands** — the repo has no source code or tooling.
- **No dependencies to install** — no `package.json` or other dependency manifests exist.
- **Static-only** — no backend, no database, no external APIs (except Google Fonts CDN for the Nunito font).
- **Path prefix matters** — assets are loaded from `/undervisningsopplegg/` so you cannot serve `index.html` from the root without adjusting paths or using a symlink/proxy.
