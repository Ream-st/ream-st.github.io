<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo.svg">
    <img src="https://raw.githubusercontent.com/Ream-st/.github/main/assets/logo.svg" width="229" height="64" alt="Ream.st">
  </picture>
</p>

# ream-st.github.io

### *Forwards Ream.st's GitHub Pages address to its GitHub organisation.*

Anyone who visits [ream-st.github.io](https://ream-st.github.io) is sent straight on to
[github.com/Ream-st](https://github.com/Ream-st), where the org profile lists every Ream.st site and repository.
The sites themselves live at [ream.st](https://ream.st), and their live status at
[status.ream.st](https://status.ream.st).

## How it works

`index.html` is a one-line page with a `<meta http-equiv="refresh">` redirect (delay `0`) and a matching
`<link rel="canonical">`, both pointing at `https://github.com/Ream-st`. To change where it forwards, edit both
URLs in `index.html`.

`.github/workflows/pages.yml` publishes the repo to GitHub Pages with Actions on every push to `main` (Settings >
Pages > Source: GitHub Actions). Actions are used instead of the old branch-deploy build, because that build can
silently stop triggering with no log anywhere.

## Related repositories

- [.github](https://github.com/Ream-st/.github) — the org profile this page forwards to
- [Website](https://github.com/Ream-st/Website) — ream.st
- [Status](https://github.com/Ream-st/Status) — status.ream.st

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Versioning

This project uses [Date Versioning](https://datevers.ing): each release is numbered by its UTC release date as `YY.MM.DD` (for example `26.10.23`), with `-1`, `-2`… for later releases the same day. See [CHANGELOG.md](CHANGELOG.md) for what changed in each release.

## License

&copy; 2026 Stux.Group. All rights reserved. This repository is not licensed for reuse or redistribution.

---

*Built & Maintained by <img src="https://global.media.ream.st/icon.png" height="14" alt="Ream.st" valign="middle"> [Ream.st](https://github.com/Ream-st).
Ream.st is a part of the <picture><source media="(prefers-color-scheme: dark)" srcset="https://global.media.stux.group/icon-light.png"><source media="(prefers-color-scheme: light)" srcset="https://global.media.stux.group/icon-dark.png"><img src="https://global.media.stux.group/icon-dark.png" height="14" alt="Stux.Group" valign="middle"></picture> [Stux.Group](https://github.com/StuxGroup) Brand of Companies.*
