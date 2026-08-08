# TrackPro V2

TrackPro V2 is the Sim Coaches Windows app for sim racers who want one place to set up their hardware, review laps, watch onboard video, compare telemetry, and manage their racing data.

## Download

Download the latest signed installer from the [TrackPro V2 releases page](https://github.com/SimCoaches/TrackProV2/releases/latest).

TrackPro updates are delivered through this public release channel. The app checks the latest release, shows the changelog, downloads the signed installer, applies the update, and restarts.

Latest release: TrackPro V2 2.26.97.

### What's New in 2.26.97

- Added Wheel Studio for designing reusable steering-wheel LED profiles and dash displays across supported devices, with themes, typed conditions, live previews, and expanded hardware backends.
- Wheel Studio is protected by testing access code `1994` and unlocks only for the current app run, matching the Motion testing gate.
- Added commanded platform-pose output for VR motion compensation plus Unity motion-integration documentation and an example sender.
- Improved ACC and rFactor 2 telemetry for tyre, timing, flag, session, and scoring data used by dashboards.
- Replaced native select menus with TrackPro's in-app selector to avoid WebView2 popup failures, and improved Event Mode kiosk and attendant reliability.
- Fixed false "went dark" alerts by recording clean title-bar exits and reporting rejected shutdown records to diagnostics.

## What TrackPro Does

- Sets up and calibrates supported Sim Coaches hardware.
- Shows live device status for pedals, motion, receiver search, and sim connection.
- Records and reviews laps with telemetry and onboard video.
- Displays speed, throttle, brake, clutch, steering, gear, lap data, and track maps.
- Helps drivers compare sessions and spot areas to improve.
- Keeps customer releases in one signed, updateable Windows installer.

## Requirements

- Windows 10 or Windows 11.
- A supported sim and supported Sim Coaches hardware for live hardware features.
- Internet access for sign-in, cloud sync, downloads, and updates.

Some setup and review screens can open without an active connection, but account, cloud, release, and online comparison features require internet access.

## Release Notes

Customer-facing changes are listed in [CHANGELOG.md](./CHANGELOG.md). Installer files are published as GitHub Release assets rather than committed to this repository.

## About This Repository

This repository hosts TrackPro V2 download information, the customer changelog, and signed release assets.
