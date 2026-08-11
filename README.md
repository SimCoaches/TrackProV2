# TrackPro V2

TrackPro V2 is the Sim Coaches Windows app for sim racers who want one place to set up their hardware, review laps, watch onboard video, compare telemetry, and manage their racing data.

## Download

Download the latest signed installer from the [TrackPro V2 releases page](https://github.com/SimCoaches/TrackProV2/releases/latest).

TrackPro updates are delivered through this public release channel. The app checks the latest release, shows the changelog, downloads the signed installer, applies the update, and restarts.

Latest release: TrackPro V2 2.26.105.

### What's New in 2.26.105

- One-time driver setup now belongs to each account: signing in on a PC where someone else already finished setup no longer skips yours, and signing in mid-session routes you into setup if yours was never finished.
- Fixed shared-PC settings bleed: a newly signed-in account can no longer inherit another driver's coach and spotter settings.
- The final setup screen can no longer be missed by closing the app right after the radio check — setup resumes there on the next launch.
- Fixed ACC lap saving: laps driven in Assetto Corsa Competizione are now captured and saved (on-track detection previously discarded every ACC lap).
- Race Pass now shows a full XP history — every award this season with time, description, and +XP, grouped by day.
- Race Pass tiers continue past 100: Elite tiers progress at 2.5x XP cost, with tiers 1-100 and all rewards unchanged.
- The "active on another PC" screen now appears only when TrackPro is actually running on another PC; a claim left behind by a closed app is taken over silently.
- The sign-in page got the welcome-flow treatment: your coach is on the left of the screen, waiting with the radio.
- Fixed drivers dropping to offline or "went dark" mid-session: TrackPro minimized behind the sim no longer throttles its own heartbeats, and noisy diagnostics can no longer drown them out — Online and On-track status now hold through multi-hour stints.

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
