# Changelog

## TrackPro V2 2.26.42 - 2026-07-02

- Added the AI Coach and Spotter overhaul with stronger spotter accuracy, less repeated callouts, and richer live coaching context from recent laps.
- Improved Coach personalities so Encouraging, Technical, Tough Love, and Race Engineer modes respond with clearer, more distinct guidance.
- Added reciprocal community corner-data sharing: drivers can turn sharing off to keep their data private, and community reference data is only returned to drivers who also share.
- Redeployed the live AI Coach voice and realtime token services with the updated prompts and tools.
- Verified Buttkicker/bass-shaker output support in the haptics engine, including preferred handling for ButtKicker USB Amp devices.
- Hardened the corner-composite RPC so anonymous callers cannot read community corner reference data.

## TrackPro V2 2.26.33 - 2026-06-10

- Fixed a rare system crash (blue screen) that could occur when the Sim Coaches pedal driver was updated, repaired, or disabled. The virtual pedal driver now shuts down cleanly in every case.
- The installer now reliably updates the Sim Coaches virtual pedal driver to the latest version on PCs that already had it installed, completing the update safely after the next reboot. Previously some PCs could keep running an older driver even after updating.
- Fixed an iRacing controls/calibration freeze risk that could happen when the virtual pedal device stopped responding. TrackPro now checks that the pedal output is working, rebuilds the virtual pedal device if needed, and — if it still won't respond — leaves your physical pedals available instead of getting stuck.
- Reduced log noise from a bad pedal-driver session so problems are recorded as periodic health checks instead of flooding the logs.
- Fixed motion controller startup so TrackPro no longer scans, opens, or falls back to Thanos/ESP32 serial controllers while motion is idle. TrackPro now opens motion hardware only when you start, test, or calibrate motion, and releases the serial port when motion is stopped.
- Added a support diagnostic option to help troubleshoot controller-enumeration issues.

## TrackPro V2 2.26.30 - 2026-06-10

- Fixed stuttery game frame pacing while TrackPro was running. The ambient lighting screen sampler was capturing the desktop in the background even when ambient lighting was off; it no longer captures anything unless ambient lighting is enabled with a selected light.
- Rebuilt ambient screen capture on GPU-based desktop duplication, so screen-driven ambient lighting now runs during races without affecting smoothness. Older capture is kept only as a fallback for remote desktop and rotated displays.
- Improved Govee light discovery so lights are found more reliably, including lights known to the Govee Desktop app and lights that only answer direct network scans.
- Added ambient lighting quick actions (toggle lighting, hold idle, dark mode, acknowledge low fuel, reset output/mask) for StreamDeck-style control mapping.
- Added a control mode for ambient lighting: Full Control (lights follow the screen and effects) or Effects First (lights only react to alerts and overrides).
- Added behavior settings for unselected lights: leave them alone, turn them off, or hold a fixed color.

## TrackPro V2 2.26.29 - 2026-06-09

- Fixed pedals that showed in Windows but produced no output after upgrading from an older TrackPro. The installer now automatically frees your Sim Coaches pedals from the device-hiding the old version left behind, so they work right away.
- This cleanup is automatic and safe: it leaves your other software alone and never removes drivers, so it cannot affect your keyboard or mouse.

## TrackPro V2 2.26.27 - 2026-06-09

- Added built-in Remote Support so Sim Coaches can help you directly on your sim PC: generate a one-time access code from the Remote Support page and read it to our team; no TeamViewer or other third-party tools needed.
- Added a one-time guided setup for Remote Support with a single administrator approval; nothing extra appears on your PC afterwards.
- Added an instant-access option so approved Sim Coaches staff can assist unattended rigs when you enable it.
- Improved Remote Support reliability with live online status for support sessions.

## TrackPro V2 2.26.23 - 2026-06-08

- Made Live AI Coach more useful in races with proactive spotter-style calls for traffic, fuel, gaps, and incidents.
- Added iRacing race-control tools for Coach, including cautions, black-flag clears, EOLs, wave-bys, pit open/close, grid controls, restarts, chat controls, and admin changes when the driver has session rights.
- Added Coach controls for iRacing black boxes, including relative, fuel, tires, pit adjustments, in-car adjustments, radio, and weather pages.
- Improved Community voice behavior so Coach push-to-talk temporarily mutes Community voice, and an optional setting lowers Community voice while Coach or Spotter is talking.
- Moved persistent Community voice controls into the top bar so voice stays available across TrackPro pages without covering page content.

## TrackPro V2 2.26.22 - 2026-06-07

- Fixed intermittent pedal input spikes that could briefly flash the raw pedal output and affect pressure in-game.
- Kept Community voice connected when switching away from the Community page.
- Improved Community voice controls so active drivers can manage mute, deafen, device refresh, and disconnect from other pages.

## TrackPro V2 2.26.21 - 2026-06-07

- Fixed Community voice output selection so headset routing failures are detected instead of silently playing through the wrong Windows output.
- Improved the headphone test so it reports when Windows falls back to the default speaker.
- Added guidance for Bluetooth headsets that expose separate Stereo and Hands-Free outputs.
- Fixed slow startup caused by abandoned onboard video uploads being retried on launch.
- Changed automatic onboard video capture so failed uploads are discarded instead of stored for future retry.

## TrackPro V2 2.26.20 - 2026-06-07

- Fixed Community voice join when a saved headset, microphone, or speaker device is no longer connected.
- Kept voice settings available after a failed join so drivers can switch devices and retry.

## TrackPro V2 2.26.19 - 2026-06-07

- Fixed Community voice chat so drivers in the same voice channel can hear one another.
- Improved voice playback resume and speaker routing for selected Windows output devices.

## TrackPro V2 2.26.18 - 2026-06-07

- Added Driver Lab, a structured driver-improvement course with progress tracking, telemetry drills, and a required focused human-review checkpoint.
- Added telemetry-based proof checks so Driver Lab drills measure real driving behavior instead of relying only on manual completion.
- Added coach review context for Driver Lab checkpoints so coaches can confirm whether the lesson focus matches the driver's real issue.
- Fixed Simagic P-HPR pedal reactor testing so the Pedals page targets the USB pedal reactor controller instead of the under-seat haptics output.
- Fixed duplicate Simagic haptic device entries by using the live USB HID device list.

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
