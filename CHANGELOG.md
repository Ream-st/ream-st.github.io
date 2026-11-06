# Changelog

All notable changes to ream-st.github.io are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Date Versioning](https://datevers.ing) since v26.10.23 (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## v26.11.06

### Added

- `.gitattributes`, which keeps `commit.bat` in CRLF line endings (Windows batch files can misbehave with LF-only endings)

### Changed

- The README describes this repo (a redirect from ream-st.github.io to github.com/Ream-st) instead of a generic redirect template that pointed at `example.com`, with links to ream.st, status.ream.st and the related repositories, and the Stux.Group copyright in place of "feel free to use this template"
- New branch flow: work and releases go onto `test` and reach `main` only through a pull request. `commit.sh`/`commit.bat` refuse to release on `main` and print the push and pull-request commands, and CONTRIBUTING describes the flow

### Fixed

- The README and CONTRIBUTING logo was a broken image (it linked into the private Website repo). Both now show the light/dark Ream.st logo from the public `.github` repo
- `commit.bat` had LF-only line endings; it's CRLF again

## v26.10.23

### Added

- `tests/version.sh`, which checks that `VERSION.md` is a valid Date Version, a real calendar date not in the future, and the same as the newest entry in this changelog

### Changed

- Switched from Semantic Versioning to [Date Versioning](https://datevers.ing): releases are numbered by their UTC release date as `YY.MM.DD`, with `-1`, `-2`… for later releases the same day. This release follows v1.0.2
- `commit.sh` and `commit.bat` refuse a `VERSION.md` that isn't a valid Date Version or is dated in the future (UTC), and warn when it's dated before today
- `README.md` and `CONTRIBUTING.md` describe Date Versioning and the release steps

## v1.0.2

### Fixed
- `README.md`/`CONTRIBUTING.md` load the Ream.st logo straight from the Website repo; Website v3.0.0 moved it
  from `assets/logo.svg` to `public/assets/logo.svg`, so the links now point there.

## v1.0.1

### Fixed
- GitHub Pages was using the legacy branch-deploy build system, which can silently stop auto-deploying with no error recorded anywhere (discovered on SeasonalOverlaysLibrary — its live site served stale content for over an hour with no visible failure). Switched to GitHub Actions-based Pages deployment (`.github/workflows/pages.yml`), making every deploy an ordinary, observable CI run instead.

## v1.0.0

### Added
- Initial GitHub Pages redirect repo for Ream.st, redirecting `ream-st.github.io` to `github.com/Ream-st` — `VERSION.md`/`CHANGELOG.md`/`CONTRIBUTING.md`/`commit.sh`+`commit.bat` added, following the standard release-flow convention used across other Stux.Group family repos.
