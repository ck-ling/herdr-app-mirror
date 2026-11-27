# herdr-app mirror

Unofficial mirror of the [Herdr desktop app](https://github.com/herdrdev/herdr-app) and [herdr-core](https://github.com/herdrdev/herdr-core) releases.
The official builds live on `releases.herdr.dev`. This repo copies them into GitHub Releases, and serves an update feed for them.

The `mirror` workflow checks for new versions every hour, the same interval at which the app checks this feed.
It checks each download against the upstream sha256 before it publishes.
Run it by hand from the Actions tab to mirror one version now.

## Platforms

- Windows x64: `herdr-app-windows-x86_64.zip` (app releases, `v*`) and `herdr-core-windows-x86_64.zip` (core releases, `core-v*`)
- zsh for Git for Windows: MSYS2's `zsh-<version>-x86_64.pkg.tar.zst` and its `.sig` (releases `zsh-v*`), from the `zsh` workflow every Monday. It checks the `.sig` against MSYS2's packager and master keys before it publishes, and never takes the latest mark.

## Install on Windows

1. Download `herdr-app-windows-x86_64.zip` from the latest `v*` release.
2. Extract it, and keep the `herdr-app` folder whole.
3. Run `herdr-app\herdr-app.exe`. On first start, it offers to install herdr-core.

## Update from this mirror

The app and the core read the release server from `HERDR_RELEASES_URL`.
Set it to this repo's feed, and both update from here, not from `releases.herdr.dev`:

```powershell
[Environment]::SetEnvironmentVariable("HERDR_RELEASES_URL", "https://raw.githubusercontent.com/ck-ling/herdr-app-mirror/updates", "User")
```

Sign out and in again, or restart Explorer, so that apps started from the Start menu see it.
To install through the feed instead of the zip:

```powershell
$env:HERDR_RELEASES_URL = "https://raw.githubusercontent.com/ck-ling/herdr-app-mirror/updates"
irm "$env:HERDR_RELEASES_URL/app/install.ps1" | iex
```

The feed lists only the platforms mirrored here.
Whoever controls this repo controls what the feed installs.

Herdr is licensed under Apache 2.0. Each release includes `LICENSE` and `THIRD-PARTY-NOTICES`.
