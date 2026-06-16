# dust-bucket

[![Tests](https://github.com/SettingDust/dust-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/SettingDust/dust-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/SettingDust/dust-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/SettingDust/dust-bucket/actions/workflows/excavator.yml)

A [Scoop](https://scoop.sh) bucket for CodeNomad Tauri Windows builds.

## Included manifests

- `codenomad`: stable CodeNomad Tauri build.
- `codenomad-nightly`: nightly / prerelease / development CodeNomad Tauri build.

Nightly and prerelease builds may be unstable. Use `codenomad-nightly` only when you want early builds or need to test upcoming changes.

## Add the buckets

```pwsh
scoop bucket add dust-bucket https://github.com/SettingDust/dust-bucket
```

## Install

Stable release:

```pwsh
scoop install dust-bucket/codenomad
```

Nightly / prerelease release:

```pwsh
scoop install dust-bucket/codenomad-nightly
```

## Update

Update Scoop, buckets, and installed apps:

```pwsh
scoop update
scoop update codenomad
```

If you installed the nightly manifest:

```pwsh
scoop update codenomad-nightly
```

## Uninstall

```pwsh
scoop uninstall codenomad
```

Or, for the nightly manifest:

```pwsh
scoop uninstall codenomad-nightly
```

Remove this bucket when you no longer need it:

```pwsh
scoop bucket rm dust-bucket
```

## Tests and Excavator

This bucket keeps the standard Scoop bucket automation from the original template:

- **Tests** run through `.github/workflows/ci.yml` on pushes, pull requests, and manual dispatches. The workflow runs `bin/test.ps1` on Windows with both Windows PowerShell and PowerShell Core.
- **Excavator** runs through `.github/workflows/excavator.yml` on manual dispatch and every four hours. It uses ScoopInstaller's GitHub Actions automation to check manifests for updates and open update changes when needed.

## Contributing

For manifest changes, follow Scoop's [Contributing Guide](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md) and [App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) guidance.

Before opening a pull request, run the bucket tests locally from the repository root:

```pwsh
pwsh ./bin/test.ps1
```
