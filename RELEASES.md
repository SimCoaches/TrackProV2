# Releases

TrackPro V2 customer installers are published from GitHub Releases in this repository.

## Required Release Assets

Each customer release should include:

- `TrackPro_<version>_x64-setup.exe`
- `TrackPro_<version>_x64-setup.exe.sig`
- `latest.json`

The installer must be signed by Sim Coaches before it is published. The `.sig` file must be generated after the final signed installer is created, because it covers the exact bytes the app downloads.

## Update Feed

TrackPro checks this file:

```text
https://github.com/SimCoaches/TrackProV2/releases/latest/download/latest.json
```

`latest.json` points the app to the installer asset for the current release and includes the customer changelog shown in the update prompt.

## Public Content Rules

- Keep release notes clear and customer-facing.
- Explain what changed, not how private systems work.
- Do not publish source code, private service configuration, signing material, driver internals, or internal build logs.
- Do not commit installer binaries directly to the repository.
