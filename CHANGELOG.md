# Changelog

## TrackPro V2 2.26.17 - 2026-06-06

- Restored reliable telemetry capture and lap saving for live iRacing sessions.
- Fixed onboard video saving/uploading so captured laps can include synced video.
- Restored saved-lap coach submissions from the current telemetry pipeline.
- Fixed Simagic haptic reactors so only the three supported pedal outputs are exposed.
- Improved ESP32 and Thanos motion-controller behavior.

## TrackPro V2 2.26.6 - 2026-05-24

TrackPro V2 is the Sim Coaches Windows app for hardware setup, lap review, onboard playback, telemetry, and driver improvement.

- Updated the release channel to `2.26.6` so every `2.26.5` install can see this update.
- Made update checks start faster after app launch.
- Added an obvious update pop-up when a new TrackPro build is available.
- Added a persistent `Update Available` button in the title bar so users can reopen the updater after dismissing it.
- Improved update notes so the app shows the current release section first.

## TrackPro V2 2.26.5 - 2026-05-24

TrackPro V2 is the Sim Coaches Windows app for hardware setup, lap review, onboard playback, telemetry, and driver improvement.

- Updated the release channel to `2.26.5`.
- Replaced the bundled driver payload with the Microsoft-signed Sim Coaches VHID and HID Filter driver packages.
- Added installer cleanup for TrackPro V1 leftovers, including legacy `TrackPro_v*.exe`, old shortcuts, startup entries, HidHide, and vJoy artifacts.
- Hardened the installer release gate so required drivers, FFmpeg, legacy cleanup, safe upgrade behavior, and update signing guards are validated before customer builds.
- Kept normal uninstall/update behavior from tearing down active Sim Coaches kernel drivers during app replacement.

## TrackPro V2 2.26.4 - 2026-05-24

TrackPro V2 is the Sim Coaches Windows app for hardware setup, lap review, onboard playback, telemetry, and driver improvement.

- Updated the release channel to `2.26.4`.
- Hardened the installer upgrade path so it performs a safe in-place repair and never runs an older TrackPro uninstaller during app replacement.
- Changed normal uninstall/update behavior so TrackPro leaves Sim Coaches kernel drivers installed instead of tearing down live drivers during app replacement.
- Fixed in-sim overlays so enabled widgets open in a real click-through overlay host instead of only showing an in-app preview.
- Reworked the overlays page with live previews, clearer controls, and telemetry-linked widgets for pedals, braking, track position, timing, race state, fuel, and coach cues.
- Added social profile, direct message, presence, and marketplace groundwork for the community features.
- Updated Marketplace so free members can browse redacted listings while Premium members unlock prices, seller details, messages, offers, reviews, selling, and checkout.
- Clarified seller payment options: Stripe checkout is optional, PayPal/Zelle/manual payments can be arranged directly, and Sim Coaches does not take a marketplace commission or assume transaction risk.
- Restored Sim Coaches branding inside the app and loading screen while keeping TrackPro as the product name and Windows desktop, taskbar, and tray icon.
- Fixed installer desktop shortcut cleanup so stale `trackpro-ui` shortcuts from local/dev builds are removed and the selected desktop shortcut opens the installed TrackPro app.
- Added signed customer installer delivery through the public TrackPro V2 release channel.
- Added in-app update notifications with changelog display before install.
- Added automatic download, install, and restart flow for TrackPro updates.
- Included the required Microsoft-signed Sim Coaches driver packages.
- Included onboard video capture support for lap review.
- Strengthened release checks for driver files, video capture support, and update signatures.

## 2.26.1 - 2026-04-14

- Maintenance release for TrackPro V2.
