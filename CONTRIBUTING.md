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

## Branches and going live

- **`main` is what's live.** Nothing is pushed to it directly: it only changes when a pull request from `staging` is merged. GitHub Pages only publishes from `main`.
- **`staging` is the last check before live.** It only changes when a pull request from `test` is merged.
- **Work happens on `test`**, or on a feature branch off `test` that's merged back into it. Releases are made on `test` too; `commit.sh` / `commit.bat` refuse to run on `staging` or `main`.
- **Going live:** push `test` with its tag, open a pull request into staging (`gh pr create --base staging --head test`), check staging once it's merged, then open one from staging into main (`gh pr create --base main --head staging`). Leo reviews and merges both, with merge commits, so the release tags made on `test` stay in `staging`'s and `main`'s history.

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes. It refuses to run on `main` or `staging`.
   Then push with `git push origin test --tags` and open a pull request from `test` into `staging`;
   once that's merged and checked, open one from `staging` into `main` (see [Branches and going live](#branches-and-going-live)).

## Before committing

- Open `index.html` in a browser and confirm the redirect fires correctly
