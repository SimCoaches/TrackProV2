# TrackPro V2

TrackPro V2 is the Sim Coaches Windows app for sim racers who want one place to set up their hardware, review laps, watch onboard video, compare telemetry, and manage their racing data.

## Download

Download the latest signed installer from the [TrackPro V2 releases page](https://github.com/SimCoaches/TrackProV2/releases/latest).

TrackPro updates are delivered through this public release channel. The app checks the latest release, shows the changelog, downloads the signed installer, applies the update, and restarts.

Latest release: TrackPro V2 2.26.150. (Current beta: 2.26.157 - pre-release only; install manually or opt into the in-app Beta Channel in Settings.)

### What's New in 2.26.150

The biggest update since launch - everything from thirty beta builds, promoted after field testing:

- Home is rebuilt around your racing life: live community chat you can read and post from the dashboard, who's on track right now, League Night with one-click RSVP, your Race Pass standing with your named rival and the exact XP gap, and your coaching progress.
- League Night results are captured at the official final classification, with points scored server-side and a full audit trail.
- Chat got notifications (channel badge in the sidebar), inline YouTube players in channels and private messages, and the online bar shows every online driver.
- Reliability: lap saves and replay loads ride through momentary server congestion with automatic retries - no lap is ever lost; telemetry records a uniform 60Hz across every sim.
- Performance: post-lap onboard video work runs at idle priority so it can't steal frames from your sim at the start/finish line, and background database traffic is roughly halved.
- The AI Coach speaks with instant cached lines, knows human-reviewed track craft at fifteen circuits, and new drivers get the full coach free for 30 days.
- Assetto Corsa lap capture survives pauses and restarts; track and car names display properly everywhere.

### What's New in 2.26.120

AI Coach â€” three fixes that made the coach unusable for some drivers:

- Push-to-talk now registers every press. Wheel and controller buttons were only working on the first press of a session; after that TrackPro's own virtual pedal device masked the button and nothing reached the coach.
- You can talk to the coach again. Key-ups were being refused as "microphone unavailable" on headsets that report an idle mic as muted (Corsair VOID and similar), even when the microphone was working perfectly.
- Page navigation no longer freezes while the coach is running. Starting the coach could lock you on whatever page you were on until you restarted the app; the sidebar looked like it was ignoring clicks.

Includes the 2.26.117 fixes, which were pre-release only and never delivered by automatic update.

### What's New in 2.26.116

- Fixed third-party pedal axes being zeroed during report silence â€” a throttle held flat against its stop now holds. Silence means "unchanged", never "centered"; real disconnects are detected instantly and a frozen device is caught within seconds.
- Game-controller buttons (push-to-talk, hotkeys) are now read directly from the HID layer, eliminating a Windows-level registry-handle leak that could crash or hang long sessions.

### What's New in 2.26.114

- Fixed third-party pedals (including Fanatec ClubSport V3) disconnecting and reconnecting in a loop while idle â€” pedals that only send data when moved are no longer treated as unplugged.
- Fixed two startup crashes on PCs where TrackPro launches within a minute of Windows booting.
- Reduced background device polling and diagnostic disk writes that could interfere with pedals and controllers on USB-heavy rigs.

### What's New in 2.26.113

- Fixed third-party pedals (including Fanatec ClubSport V3) dropping out mid-corner: device detection is now push-based, eliminating the background device scans that could starve pedal reads on USB-heavy rigs. Hot-plug detection is faster than before.

### What's New in 2.26.112

- Freeze reports now identify exactly what blocked the app, so any remaining freeze can be diagnosed from a single occurrence.
- Includes all 2.26.111 fixes below.

### What's New in 2.26.111

- Fixed multi-second freezes and stalled navigation while the AI Coach was speaking or starting, and reduced background work for drivers using the free spotter or plain telemetry.
- Fixed disabled overlays continuing to process live telemetry invisibly.
- Fixed VR mirroring resource leaks, including frozen overlay frames left in the headset after closing TrackPro.
- Fixed clean app closes being misreported as crashes in reliability monitoring.
- Paint Studio is now in early access behind an access code.

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

