# Changelog

## TrackPro V2 2.26.70 - 2026-07-13

- AI Coach now keeps one configuration-specific view of the current, previous, and next corner, speaks earlier, and uses short, measured guided-lap calls without rolling into extra laps.
- Coaching now compares more than braking, including turn-in, steering/rotation, racing line, throttle application, wheel slip, and understeer/oversteer evidence when the simulator reports it.
- Added protected continuous-learning review so real telemetry and correlated radio history can improve verified coach capabilities without letting a transcript directly rewrite live behavior.
- Assetto Corsa telemetry is now captured and normalized across its complete official shared-memory surface, including per-wheel and engineering channels used by coaching, haptics, motion, and saved sessions.
- Remote Support now includes its verified helper in the installer and automatically replaces a missing or damaged local copy, avoiding setup-download failures on customer PCs.
- Online and in-sim presence now use the same member data on Community and every other page, including drivers who are active in voice chat.
- Sim Center Assetto Corsa sessions now have stronger content checks, race readiness, LAN launch coordination, race phases, and live race-control telemetry.

## TrackPro V2 2.26.69 - 2026-07-12

- AI Coach now uses exact iRacing track configurations and only speaks a turn number when the map and live position are trustworthy; uncertain layouts fall back safely instead of guessing.
- Fixed Coach track-position, corner-number, radio replay, and lap-persistence regressions introduced during recent Coach improvements.
- Added a card-required 14-day trial for new Starter, Pro, and Elite subscribers.
- Added complimentary tester memberships and single-use access codes with no card or automatic renewal.
- Added promotional membership pricing that stays locked while the original subscription remains active.

## TrackPro V2 2.26.55 - 2026-07-08

- Track distances (brake points, turn-in, approach) always spoken in meters so they match race boards and markers.
- Speeds still default to mph; toggle Settings to metric for kph.

## TrackPro V2 2.26.54 - 2026-07-08

- Pre-corner cues fire earlier so you hear brake/setup notes while preparing, not after you're already on the brakes.
- Speed coaching gives a real target ("aim about 60 mph mid-corner") plus the delta vs your last pass — not only "+9 mph more."
- Speeds default to mph; distances use meters to match track boards (refined further in 2.26.55).
- Removed confusing "you'll be at Turn X in about N seconds" countdowns (they were a rough distance÷speed guess and often wrong once you brake).

## TrackPro V2 2.26.53 - 2026-07-08

- Fixed pre-corner coaching language: approach cues now say what to do next ("brake about 15 meters later") instead of diagnosing a brake you haven't made yet ("15 meters early on the brakes").
- While working one focus corner, pre-corner radio no longer calls secondary corners you aren't coaching.
- Clearer live position for the coach: "where am I" uses the live landmark snapshot and should not invent a different corner from chat history.
- Outlap stays quiet for unprompted coaching (tires, warmup). Proactive technique radio starts on the first flying lap after you cross start/finish; if you key the radio and ask, the coach still answers.
- Hardened pin/switch, guided-lap phrasing, and delivery so cues are less likely to fire at the wrong moment or double-talk.

## TrackPro V2 2.26.52 - 2026-07-08


- Live AI Coach focus: ask to work on a corner (e.g. "focus on Turn 4") and coaching sticks there immediately — no more "we can't switch" style pushback.
- Cleaner pre-corner radio: measured distances stay realistic (no absurd hundred/thousand-meter callouts), and open tips no longer spam other corners while you're focused on one.
- If a fix isn't landing, the coach escalates how it teaches the same corner (pressure, sequence, eyes) instead of only repeating the same one-liner.
- Instant post-corner feedback is more honest: one good pass is "on the mark"; "that's fixed" waits until you've held it for two clean laps.
- Live voice cost/quality tiers: Starter uses the efficient Realtime mini model; Pro and Elite use full Realtime 2.1 for the best tool-following coach.

## TrackPro V2 2.26.49 - 2026-07-08


- Proactive corner cues now include the measured figure ("you're about 15 meters late on the brakes") for the technical coach, so you get the number without asking.
- Gear coaching: ask what gear to be in and the coach compares the reference's apex gear to yours; it can always report your current gear.
- Consistent reference answers: the coach explains the reference the same way every time (a per-corner best composite from laps as quick as a stated time) instead of flip-flopping on whether it has a lap time.
- "Was that an improvement?" asked mid-lap now returns "finish the lap and I'll confirm" instead of sounding blind.
- Start Coach no longer fails silently — it tells you when mic/headphones need setup and points to Voice Setup.
- All existing laps in the database now feed the coach's reference pool, so faster reference data is available without waiting for owners to re-run the app.

## TrackPro V2 2.26.48 - 2026-07-08

- Fixed Start with Windows: TrackPro now repairs its own startup entry on every launch (stale paths after reinstalls/updates), respects your opt-out and Task Manager disables, and starts quietly in the tray without flashing a window at login.
- Community Voice channels now show who's inside (names and avatars) before you join, refreshing every few seconds on the Community page.
- Fixed the AI coach failing to load reference laps: coach memory is now per account, your previously saved laps seed the reference data automatically after sign-in, and a new session best becomes the comparison target within seconds.
- "Where am I losing time" now falls back to comparing against your own best pass this session (and says so) instead of refusing when no stored reference exists yet.
- Locked down a database table that was readable outside the app (RLS enabled; no user action needed).

## TrackPro V2 2.26.47 - 2026-07-07

- Fixed the AI coach believing a full-course yellow / pace order was active in solo Test Drive and practice sessions (misread iRacing pace-mode signal); the coach now knows the session type and when you are alone on track.
- Fixed the coach placing you 1-2 corners behind: forward-phrased position, corrected corner resolver, and about half a second less latency on every voice question.
- Corner questions now work for corners ahead: "turn 10" resolves on tracks with named corners, answers state where the corner is relative to you, and saved/community reference laps load reliably mid-session.
- Fixed the faint robotic background voice reading off-track tallies; off-track history now resets each session and never forces computer text-to-speech.
- Coaching advice is now driver-relatable (relative, rounded distances and gears) instead of raw track coordinates, and the coach starts proactive focus coaching within a couple of laps on any track.
- Added the Corner Naming setting: numbers by default ("Turn 3"), traditional names opt-in, switchable from the Coach page or by voice; the spotter no longer reads corner names.
- Fixed multi-source track maps so iRacing-exact corner data wins (Red Bull Ring now uses all 10 corners).

## TrackPro V2 2.26.44 - 2026-07-03

- Added the track-edge model foundation for spatial racing-line analysis, including canonical centerline/edge geometry, signed lateral offset, and line-fault detection.
- Added Telemetry page spatial line notes and official-edge rendering support, with graceful fallback to the driver's own lap model when imported map data is unavailable.
- Added live predictive coach cues that can speak upcoming corner and racing-line guidance from the new track model.
- Seeded Supabase with surveyed TUM track-edge data for 25 circuits and redeployed the realtime coach token service.
- Published a fresh signed installer and updater feed for TrackPro V2 2.26.44.

## TrackPro V2 2.26.43 - 2026-07-03

- Added AI Coach improvement tracking with persistent driver skill snapshots, structured coaching tips, and coach usage linked to telemetry sessions.
- Improved post-session insights with real improvement velocity, lap-time trend, and coaching follow-through counters.
- Updated Live AI Coach usage metering so unlimited plans still record analytics rows without charging quota.
- Removed dead credentialed AI coach completion and compaction function cleanup from the deployed Supabase surface.
- Published a fresh signed installer and updater feed for TrackPro V2 2.26.43.

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
