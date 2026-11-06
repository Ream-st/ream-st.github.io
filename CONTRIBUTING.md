<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo.svg">
    <img src="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo.svg" width="229" height="64" alt="Ream.st">
  </picture>
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

## Branches

- Work goes onto `test` (or a feature branch off it), never straight onto `main`.
- Changes reach `main` only through a pull request from `test` into `main`, which Leo reviews and merges. Merge it
  with a merge commit, so the release tags made on `test` stay in `main`'s history.
- GitHub Pages only publishes from `main`, so a release goes live when its pull request is merged.

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes. It refuses to run on `main`.
   Then push with `git push origin test --tags` and open a pull request from `test` into `main`.

## Before committing

- Open `index.html` in a browser and confirm the redirect fires correctly
