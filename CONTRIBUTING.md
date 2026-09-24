<p align="center">
  <img src="https://raw.githubusercontent.com/Ream-st/Website/main/public/assets/logo.svg" height="80" alt="Ream.st Logo">
</p>

# Contributing to ream-st.github.io

This is a minimal GitHub Pages redirect page (`index.html`) that forwards visitors from `ream-st.github.io` to [github.com/Ream-st](https://github.com/Ream-st). This document is for anyone working on the redirect page itself.

## Local setup

There's no build step or dependencies — just open `index.html` in a browser, or serve the directory with any static file server, e.g.:

```bash
python3 -m http.server 8000
```

## Project conventions

- Single static `index.html` — no framework, no build step, no backend.
- Keep it minimal; this repo exists only to redirect GitHub Pages traffic.

## Versioning and changelog

- The version lives in `VERSION.md` (a bare version string) — bump it on every release, following [Semantic Versioning](https://semver.org/)
- Every release gets a `CHANGELOG.md` entry using `### Added` / `### Changed` / `### Fixed` subsections
- `commit.sh` (bash) and `commit.bat` (Windows) read `VERSION.md` to commit and tag a release — no need to edit them per release

## Before committing

- Open `index.html` in a browser and confirm the redirect fires correctly
