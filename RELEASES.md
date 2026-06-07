# Release Channel

This public repository, `SimCoaches/TrackProV2`, is the customer release
channel for TrackPro V2.

The private source repository is `SimCoaches/trackpro-v2`. Source code, build
scripts, internal documentation, private service configuration, and release
tooling stay there. Customer installers do not get published from the private
repository.

TrackPro V2 customer installers are published from GitHub Releases in this
public repository:

```text
https://github.com/SimCoaches/TrackProV2/releases
```

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

## Publishing Rules

- Build, sign, and verify installers from the private source checkout.
- Publish the signed installer, updater `.sig`, and `latest.json` to this
  public repository's GitHub Releases.
- Mark the current customer release as the latest release.
- Keep release notes clear and customer-facing.
- Do not upload customer installers to `SimCoaches/trackpro-v2`.
- Do not commit installer binaries directly to this repository.

## Public Content Rules

- Keep release notes clear and customer-facing.
- Explain what changed, not how private systems work.
- Do not publish source code, private service configuration, signing material, driver internals, or internal build logs.
- Do not commit installer binaries directly to the repository.
