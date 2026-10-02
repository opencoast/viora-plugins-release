# Viora release

This repository is the public face of Viora. It is not the application source.

[viora.opencoast.io](https://viora.opencoast.io) is this branch, served by GitHub Pages. `.nojekyll` is here so Pages serves the files as they are.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The homepage, including the download buttons. |
| `app.json` | The desktop version the app checks, and the installer links. |
| `store.json` | The plugin catalog the app installs from. |
| [Releases](https://github.com/opencoast/viora-release/releases) | The installers and `.vplugin` packages. The git tree does not contain those binaries. |

## Desktop packages

`app.json` names the current product version and one row for each published platform.

- `version` is what an installed copy compares. A newer build of the same version updates the download, and is not treated as an update.
- `packages[].sha256` is the zip or the Windows installer.
- `packages[].appSha256` is `resources/app.asar` inside that package. `official` keeps every asar hash that has been published, including ones whose installer row has since been replaced. A running copy whose asar is not in that list is marked Unofficial.

Desktop release tags look like `viora-v1.0.0-build.10`.

## Plugins

`store.json` is the catalog at [viora.opencoast.io/store.json](https://viora.opencoast.io/store.json). Each entry points at a `.vplugin` on a Release, with its `sha256` and `size`. The `viora` field is the application version that package requires.

Plugin release tags look like `doujin-galleries-v1.0.8`.
