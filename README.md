# herdr-app mirror

Unofficial mirror of the [Herdr desktop app](https://github.com/herdrdev/herdr-app) releases.
The official builds live on `releases.herdr.dev`. This repo copies them into GitHub Releases.

The `mirror` workflow checks for a new version every 6 hours.
It checks each download against the upstream sha256 before it publishes.
Run it by hand from the Actions tab to mirror one version now.

## Platforms

- Windows x64: `herdr-app-windows-x86_64.zip`

## Install on Windows

1. Download `herdr-app-windows-x86_64.zip` from the latest release.
2. Extract it, and keep the `herdr-app` folder whole.
3. Run `herdr-app\herdr-app.exe`.

The app updates itself from `releases.herdr.dev`.
It needs [herdr-core](https://github.com/herdrdev/herdr-core), and offers to install it on first start.

Herdr is licensed under Apache 2.0. Each release includes `LICENSE` and `THIRD-PARTY-NOTICES`.
