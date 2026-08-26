# Changelog

## TrackPro V2 2.26.128 - 2026-08-26 (beta)

- Hard THUD on gear shifts and kerb strikes: continuous effects momentarily duck out of the way while an impact fires, so the hit owns the full shaker stroke. The punch was being masked, not missing.
- ACC and Assetto Corsa road/kerb texture now plays the car's real suspension waveform (the same high-rate playback iRacing got) instead of synthesized noise.
- SIMAGIC P-HPR: the streaming path now uses the same output-route discovery as the Test button, so boards that only answer a fallback route work while driving.
- Motion settings and the enabled state survive an app restart: the saved profile loads at startup, and if motion was enabled when you closed TrackPro it re-arms on launch (waiting for telemetry behind the full safety chain; an emergency stop always cancels the re-arm).
- Motion page shows a live command-smoothness readout to separate software jitter from controller-side settings.

## TrackPro V2 2.26.127 - 2026-08-26 (beta)

- Fixed high CPU usage while pedal haptics were active — severe enough on some rigs to cause stutter or disconnects in iRacing. The SIMAGIC P-HPR writer now sends motor state only when it actually changes (with a once-per-second refresh; the feel is unchanged), and the bass-shaker audio stream uses a shaker-appropriate buffer size instead of an aggressively small one some audio drivers service expensively.

## TrackPro V2 2.26.126 - 2026-08-26 (beta)

- Driver Lab is now early access behind an access code while the course videos are in production. Existing progress is untouched; ask the Sim Coaches team for access.

## TrackPro V2 2.26.125 - 2026-08-25 (beta)

- NEW: Report Card (Racing > Report Card). Your last 30 days, measured from your own driving: time the AI Coach found you on coached corners, your improvement rate on coached vs uncoached corners, your community pace-group climb, habits fixed or fading vs still recurring, seat time, and the one thing most worth working on next. Every number is real; sections say honestly when there is not enough data yet.
- Returning accounts skip setup: if you finished account setup once, signing in on a new PC no longer re-walks the setup screens — at most you see the final plan screen once. Signed-out machines still offer account creation as before.

## TrackPro V2 2.26.124 - 2026-08-25 (beta)

- Telemetry lap loading is much lighter on the database: lap viewers, ghost overlays and comparisons request only the channels they render, and repeat views of the same lap are served from a session cache. Every telemetry channel is still captured and stored unchanged.
- Community corner references: the coach's reference layer now publishes whole-field reference cells for track/car combos with 5 or more real drivers sharing data, alongside the existing quartile ladders.
- AI Coach training system (shadow mode): a nightly server-side model learns which coaching cues actually make drivers faster from graded cue outcomes across the fleet. This build records what the model would have said next to every graded cue; it does not change what the coach says.

## TrackPro V2 2.26.123 - 2026-08-21 (beta)

- League Night: RSVP lists show who is on the grid by name on the League page and the Friday event cards, not just a count.
- The League Night card on Home is clearer: your local start time leads with the Pacific origin spelled out, the sim (iRacing) is named, and drivers without an account see that the league is free to enter and can create one from the card.
- Installer fix: installing with a third-party STM32-based wheel or button box connected no longer disturbs that device. The pedal-filter binding pass previously re-enumerated any STMicro USB device, which could knock the device or its USB port offline until reboot.

## TrackPro V2 2.26.122 - 2026-08-16 (beta)

- Staff: Coach Learning admin page for reviewing, replaying and approving the capability candidates the AI Coach mines from driver requests it could not fulfil. Nothing reaches drivers without a passing deterministic replay and a human adversarial review.

## TrackPro V2 2.26.121 - 2026-08-15 (beta)

- AI Coach answers sooner after key-up: questions held over 1.5s no longer wait for speech recognition before the coach starts thinking, and database lookups (session history, lap comparisons, fuel plans) run while the coach is still composing its answer.
- Fixed the first callout of a session coming out as a robotic computer voice — the coach's real voice clips are warmed before connect.
- Fixed a garbled or clipped first syllable when the coach first comes on the radio.
- Every coach exchange records a per-leg latency breakdown for fleet-level tuning.

## TrackPro V2 2.26.120 - 2026-08-15

- Fixed push-to-talk only registering the first press of a session on wheel and controller buttons. TrackPro publishes its own virtual pedal device, and that device was answering the button query for every binding, so the real controller was never consulted after the first press. Button reads are now matched to the device the binding was captured on.
- Fixed the AI Coach refusing every key-up as "microphone unavailable" on headsets that report an idle microphone as muted (Corsair VOID and similar). A muted reading on an idle capture proves nothing about whether audio will flow, so it no longer blocks transmitting; genuine silence is still caught by the dead-mic detector.
- Fixed page navigation freezing for as long as the AI Coach was running. A callback rebuilt on every render drove a render loop in the coach provider, which starved React Router's navigation and left the app stuck on the current page until restart.

## TrackPro V2 2.26.117 - 2026-08-15 (private beta)

- Fixed page navigation being blocked while the AI Coach is speaking or transcribing.
- The updater re-checks for the newest version at install time, so a stale prompt can never install an outdated build.

## TrackPro V2 2.26.116 - 2026-08-15

- Fixed third-party pedal axes being zeroed during report silence — including a throttle held flat against its stop. TrackPro now holds the last known pedal state while the device connection is verifiably healthy; real disconnects are detected instantly from the failed read, and a frozen device is caught by a direct liveness probe within seconds.
- Beta: game-controller buttons (push-to-talk, hotkeys) are read directly from the HID layer with persistent device handles, replacing legacy Windows joystick polling and eliminating a Windows-level registry-handle leak on rigs with frequently changing USB devices. Beta builds are published as pre-releases and are not delivered by automatic update.

## TrackPro V2 2.26.115 - 2026-08-15 (private beta, superseded by 2.26.116)

- Earlier beta of the HID-native button reading; its pedal-silence handling was incomplete and is replaced in 2.26.116.

## TrackPro V2 2.26.114 - 2026-08-15

- Fixed third-party pedals (including Fanatec ClubSport V3) showing as disconnected and reconnecting in a loop whenever they sat idle: pedals that only send data when moved were treated as unplugged after three quiet seconds. TrackPro now verifies the connection directly and leaves a healthy idle device alone.
- Fixed two startup crashes on PCs where TrackPro launches within the first minute after Windows boots.
- Fixed a background loop that re-scanned all USB devices every second when a configured haptic device was absent, and cut game-controller polling by ~95% — both could interfere with streaming pedals on USB-heavy rigs.
- Diagnostic recording no longer amplifies disk writes during device error bursts.

## TrackPro V2 2.26.113 - 2026-08-15

- Fixed third-party pedals (including Fanatec ClubSport V3) dropping out and centering mid-corner. Background device discovery re-walked the whole device tree every two seconds, which on USB-heavy rigs could starve pedal reads for 5-12 seconds. Detection is now push-based — Windows notifies TrackPro the moment hardware changes — cutting background device walks by over 99% while making hot-plug response faster.
- Slow device walks are now measured and logged so any remaining interference is diagnosable from a single field log.

## TrackPro V2 2.26.112 - 2026-08-15

- Freeze reports now include the exact main-thread tasks that blocked the app, with timing and attribution, so remaining freeze causes can be pinpointed from a single field occurrence.
- Includes all 2.26.111 fixes.

## TrackPro V2 2.26.111 - 2026-08-15

- Fixed multi-second freezes and stalled navigation while the AI Coach was speaking or starting: the coach's live machinery no longer re-runs on every spoken syllable, a spotter feedback loop that could starve the app has been broken, and coach overlay updates publish only when content actually changes. Drivers using only the free spotter or plain telemetry also benefit.
- Fixed disabled overlays continuing to process live telemetry invisibly; a hidden overlay window now costs nothing.
- Fixed VR mirroring resource leaks: the shared feed releases when mirroring turns off, headset panels retire properly, and closing TrackPro no longer leaves frozen overlay frames in the headset.
- Fixed clean app closes being misreported as crashes, so reliability monitoring reflects reality.
- Paint Studio is now in early access behind an access code.

## TrackPro V2 2.26.110 - 2026-08-14

- Fixed a critical desktop resource leak triggered by an AI Coach wheel-button push-to-talk binding. TrackPro now uses the native low-latency wheel monitor instead of repeatedly enumerating input devices, preventing freezes, black screens, lost voice chat, and pedal loss after long sessions.
- TrackPro Core now survives an unexpected app interruption as a pedal failsafe: virtual pedal output continues while you are driving, and the Pedals page can restart the engine in place without relaunching the app.
- Added native crash capture: WebView failures, Windows crash events, and black-box session state are collected automatically and included in private support bundles, so incidents can be diagnosed without manual log hunting.
- Onboard recording now checks free disk space before and during capture and stops cleanly with a clear message when the drive is almost full, instead of failing repeatedly in the background.
- Fixed immediate sign-out loops on PCs with an incorrect Windows clock by anchoring session lifetime to the local clock.
- AI Coach voice usage is now measured precisely, so short exchanges no longer round up to extra seconds against your plan.

## TrackPro V2 2.26.109 - 2026-08-14

- Fixed intermittent pedal disconnects by keeping active USB devices out of background re-enumeration and recovering third-party pedal handles without requiring an app restart.
- Fixed apparent simulator freezes after missed iRacing notifications or temporary telemetry stalls; TrackPro now resumes the existing connection instead of waiting for a reconnect cycle.
- Reduced lockup risk from repeated diagnostics by coalescing duplicate telemetry and virtual-device warnings, and corrected the page watchdog so normal navigation cannot be mistaken for a frozen screen.
- Improved background AI Coach session analysis and strategy planning while preserving the existing low-latency live radio path.

## TrackPro V2 2.26.108 - 2026-08-13

- Added production support for Fanatec ClubSport Pedals V3 connected directly by USB, including automatic discovery and correct throttle, brake, and clutch mapping.
- Rebuilt Paint Studio around each selected car's actual iRacing body map so artwork lands on recognizable body panels instead of a blank texture.
- Added car-aware paint layouts, editable multi-location custom numbers, automatic paint installation, and a responsive workspace that remains usable with the members panel open.

## TrackPro V2 2.26.107 - 2026-08-11

- The setup flow's headset step now handles a headset plugged in late: it explains that no microphone was found, watches for one, and continues by itself the moment Windows sees it — no more raw "Requested device not found" dead end.
- A remembered microphone that's no longer present falls back to the system default instead of a dead level meter.

## TrackPro V2 2.26.106 - 2026-08-11

- Fixed onboard recording restarting itself every two seconds on untimed laps (out-laps, tows): recordings now survive, and the constant background CPU and disk churn it caused is gone.
- The collapsed members rail now shows every online driver's picture (up to twelve, then a +N counter) instead of only the first four.
- Dash Studio layouts now render on the wheel's own screen (VoCore-based displays), and Moza and Fanatec wheels join device discovery.

## TrackPro V2 2.26.105 - 2026-08-11

- One-time driver setup now belongs to each account: signing in on a PC where someone else already finished setup no longer skips yours, and signing in mid-session routes you into setup if yours was never finished.
- Fixed shared-PC settings bleed: a newly signed-in account can no longer inherit another driver's coach and spotter settings.
- The final setup screen can no longer be missed by closing the app right after the radio check — setup resumes there on the next launch.
- Fixed ACC lap saving: laps driven in Assetto Corsa Competizione are now captured and saved (on-track detection previously discarded every ACC lap).
- Race Pass now shows a full XP history — every award this season with time, description, and +XP, grouped by day.
- Race Pass tiers continue past 100: Elite tiers progress at 2.5x XP cost, with tiers 1-100 and all rewards unchanged.
- The "active on another PC" screen now appears only when TrackPro is actually running on another PC; a claim left behind by a closed app is taken over silently.
- The sign-in page got the welcome-flow treatment: your coach is on the left of the screen, waiting with the radio.
- Fixed drivers dropping to offline or "went dark" mid-session: TrackPro minimized behind the sim no longer throttles its own heartbeats, and noisy diagnostics can no longer drown them out — Online and On-track status now hold through multi-hour stints.

## TrackPro V2 2.26.104 - 2026-08-11

- Radio Check is now personal: the coach answers by name in the coach voice you picked during setup, for all accounts.
- Race-day event reminder emails now send even when the only open TrackPro is a guest session.
- Message, offer, order, and RSVP emails are no longer silently skipped when the app hasn't finished signing in.

## TrackPro V2 2.26.103 - 2026-08-10

- AI Coach responds faster, carries forward prior-session work more reliably, and gives clearer guided-lap, predictive, and technique coaching with fewer contradictory or mistimed calls.
- AI Coach can now read real session history, calculate fuel plans, identify track corners, compare your own laps, report live delta, read the current garage setup, and diagnose connection, microphone, audio, and overlay state.
- Added optional named comparison with an accepted friend when both drivers explicitly enable it; private driver data remains unavailable without mutual consent.
- Spotter now stays quiet behind the pace car, warns about rapidly closing traffic, pit-exit traffic, and unsafe rejoins, and includes complete male and female voice clips for the new calls.
- Added Assetto Corsa traffic-spotter integration with automatic plugin installation and in-app activation guidance.
- Radio Check now uses a natural speaking level and supports mapped steering-wheel buttons for push-to-talk testing.
- Account billing now distinguishes the billed Stripe tier from temporary or trial access and can offer eligible subscribers a one-time 50%-off, three-month save offer before cancellation without blocking cancellation.

## TrackPro V2 2.26.102 - 2026-08-09

- TrackPro no longer launches Steam or SteamVR under any circumstances; the SteamVR integration has been removed entirely.
- Fixed a crash that could freeze the whole app and silence the coach, spotter, and radio the moment push-to-talk was pressed or coach voice connected.
- TrackPro's background engine now shuts itself down when the app closes unexpectedly, so the next launch always starts clean instead of "nothing works until reboot".
- The installer now clears stale TrackPro processes from previous sessions automatically instead of refusing to install until Windows is restarted.
- AI Coach voice now recovers automatically when a microphone (for example a VR headset mic) disconnects and later returns mid-session.
- Wheel-button push-to-talk bindings now reach the native input monitor, so coach radio works while the sim has focus.
- The app and its background engine are now code-signed, reducing antivirus and SmartScreen blocks during install.

## TrackPro V2 2.26.101 - 2026-08-07

- Improved force-feedback output under heavy steering load with dynamic-headroom mixing, safer open-loop testing, and removal of unwanted autocenter spring behavior.
- Wheel LED assignments now persist per device and render through supported hardware backends during live telemetry.
- Added a Wheel Studio device picker and live dash output for desktop and in-sim overlay displays.
- Le Mans Ultimate is now detected and identified separately from rFactor 2 across telemetry, lap uploads, coaching, and hardware profiles.

## TrackPro V2 2.26.100 - 2026-08-07

- Added a locked FFB Lab for supervised staff testing, profile control, signal-chain inspection, and session-locked Auto/Manual tuning.
- Added steering-torque acquisition for iRacing, Assetto Corsa, ACC, rFactor 2, and Le Mans Ultimate.
- Fixed stuck navigation during live sessions by coalescing high-frequency telemetry and LiveKit audio-meter updates.
- Improved overlay startup and recovery with boot-race protection, starvation detection, and broader healing coverage.

## TrackPro V2 2.26.99 - 2026-08-06

- Added native VR overlay foundations for both OpenXR and SteamVR, including an OpenXR API layer that does not require SteamVR.
- Added iRacing's 360 Hz steering-torque stream as the high-rate input for TrackPro's dormant FFB engine.
- Added an environment-gated FFB capture and deterministic replay harness for measuring detail, smoothness, clipping, and safety before hardware output is enabled.
- Added an inert-by-default DirectInput constant-force layer for explicitly enabled, capped, supervised FFB bench testing.
- Added left/right traffic calls for rFactor 2, Le Mans Ultimate, and F1 24/25.
- Fixed spotter category switches so each setting controls exactly the call family described by its label.
- Added regression coverage for the spotter settings wiring and native OpenXR loader path.

## TrackPro V2 2.26.98 - 2026-08-06

- Added a guided, resumable setup flow covering driver identity, headset and radio checks, spotter configuration, pedal calibration, and plan selection.
- Telemetry capture and valid-lap handling now work consistently across iRacing, ACC, Assetto Corsa, rFactor 2/LMU, F1, and BeamNG.
- Community comparison laps now stay within the correct simulator, preventing same-named tracks from different games from being mixed.
- Expanded Wheel Studio with device discovery, click-to-map calibration, hardware LED rendering, and verified layouts for a much larger wheel catalog.
- Motion now uses a 360 Hz control loop with predictive compensation, understeer and road-texture cues, stronger plausibility checks, and BeamNG OutSim support.
- Haptic profiles can switch automatically for each car and track.
- AI Coach and spotter controls now expose radio volume more clearly, report real usage, and make more honest lap and position calls.
- Fixed username availability checks so a driver can keep the username already assigned to their own account.

## TrackPro V2 2.26.97 - 2026-07-31

- Added Wheel Studio for building reusable steering-wheel LED profiles and dash displays, including scalable LED layouts, themes, typed conditions, live previews, and expanded hardware backends for GSI, Moza, Fanatec, WLED, SimHub-compatible, and other supported devices.
- Wheel Studio is protected by testing access code `1994`; an unlock lasts only for the current app run, matching the Motion testing gate.
- Motion now publishes commanded platform pose for VR motion-compensation integrations, with customer-facing Unity integration guides and an example telemetry sender.
- ACC now exposes the tyre, timing, flag, and session data already available from shared memory, while rFactor 2 reads its scoring buffer so dashboards no longer remain at `0:00.000`.
- Native select menus were replaced with TrackPro's in-app selector to avoid WebView2 popup failures.
- Event Mode now releases its sender port when disabled, aligns the kiosk with the standalone lap-time sender, and keeps every attendant action tied to the selected simulator.
- Fixed the false "went dark" alerts: TrackPro now records that it closed normally when you quit from the title bar, so a clean exit is no longer reported as a crash. No install had ever managed to record a clean exit, which is why healthy sessions were being flagged.
- Diagnostics now report when a shutdown record is rejected instead of failing silently.

## TrackPro V2 2.26.96 - 2026-07-26

- The startup/loading page now shows `V2.26.96` from its first paint and continues to confirm the installed version directly from the running TrackPro app.
- Failed update checks now appear in fleet diagnostics without generating unnecessary alerts for ordinary offline rigs or temporary network interruptions.
- Failed downloads or installations now report the target release to support diagnostics, making it possible to identify and help rigs stranded on an older version.
- Marketplace listing details no longer crush the browse header when the members rail is open; the header actions wrap cleanly while the title, plan badge, and tagline remain readable.

## TrackPro V2 2.26.95 - 2026-07-26

- The startup splash now reads the version directly from the running TrackPro binary, so it always identifies the version actually installed instead of showing a stale hardcoded number.
- Normal app shutdowns are now delivered immediately to fleet diagnostics, reducing false “went dark” incidents when a driver closes TrackPro normally.
- Fleet alerts now page once per distinct dark event and at most daily for an ongoing error group, preventing repeated notifications from hiding genuinely new incidents.
- TrackPro now re-checks for updates every four hours while running, so always-on simulator rigs receive new releases without needing an app restart.

## TrackPro V2 2.26.94 - 2026-07-26

- AI Coach now measures which coaching guidance improves lap performance, keeps useful anticipation cues from being demoted by unrelated metrics, and correctly includes control cues in suppression decisions.
- AI Coach now accepts gallons and PSI for pit fuel and tire-pressure commands, can recalibrate pedal-pressure guidance on request, and begins discovering each car's available in-car adjustments from live simulator data.
- Hardware and device settings now sync safely per machine, restoring a rebuilt rig without carrying its calibration to another PC or sim-center rig; personal preferences still follow the driver.
- Sim Center adds a scan-to-race arrivals desk, simulator rig mapping, and USB HID card-scanner support for faster check-in.
- Venue check-in now enforces required liability waivers, blocks revoked Driver Cards, supports replacement fees, and records waiver review provenance for front-desk staff.
- Venue progression now combines career XP with real venue visits, shows visits needed for the next rank, and reliably awards the visit when a session ends.
- Added a Works Driver program with applications, commission tracking, referral cards, and individual Stripe promotion codes so attributed sales reach the right driver.
- Messages now use a focused phone-style inbox, with more reliable realtime DMs, clearer unread counts, and a less cluttered profile page.
- Community events now support reliable RSVPs, confirmation email, and race-day reminders sent three hours before green.

## TrackPro V2 2.26.93 - 2026-07-26

- AI Coach now fills verified gaps between mapped corners with inferred straight segments, extending track-position awareness across more of the lap without inventing corner names.

- Added password and username recovery to sign-in. A driver who forgets either can now recover their account with a code sent to their email; previously there was no way back in.
- Sim Center: bookings taken on a venue's own website now appear in TrackPro, hold the right rig, and attach the driver to their own account so their laps are saved to them.
- Sim Center: introduced Driver Cards — a scannable card that lets a driver check themselves in at any simulator, with a permanent code that stays theirs across every card they are issued.
- Sim Center: added Grid Rank, earned at the venue, and Driver Class, earned from lap pace, so venue progression is not skipped by racing at home.
- Sim Center: added membership credits, including buddy passes, that refresh each billing period.
- The Race Pass season leaderboard now refreshes while you watch it instead of only when the page is opened.
- Third-party pedal rigs no longer report a missing TrackPro HID filter as an error.
- Fleet diagnostics now report install heartbeats and group recurring errors reliably so silent failures can be detected and fixed.
- Telemetry is retained indefinitely instead of being removed by an automatic retention window.
- Retired the legacy SuperLap page and removed its navigation entry.
- Driver accounts are now enforced as unique by email and username, preventing duplicate profiles for the same person.

## TrackPro V2 2.26.92 - 2026-07-25

- Race Pass now records progress for all 12 supported quest requirement types, fixing challenge categories that previously never advanced.
- The Race Pass header is more compact so the leaderboard appears higher on the page and is visible sooner.
- Personal-best lookups used by Race Pass progression now use a dedicated index for faster updates as participation grows.
- Overlay cosmetic rarities now have distinct visual treatments across both the TrackPro interface and the in-sim overlay host.
- Improved backend update reliability so Race Pass progression and future service updates stay consistent.

## TrackPro V2 2.26.91 - 2026-07-25

- Microphone setup now silences the live voice channel while testing and calibrates against the measured room-noise floor, preventing setup audio from leaking to other participants and avoiding false speech detection from fans or background noise.
- Added an opt-in microphone-level diagnostic and offline replay gate so voice tuning can be verified against real rig noise and normal speech without recording audio.
- Overlays now use **Alt+O** to switch between click-through driving mode and movable setup mode, replacing the old F8 hold-to-move behavior.
- Overlay dragging is reliable while setup mode is active, and the overlay host clearly reflects whether windows are locked or movable.
- Rebuilt the Overlays page around focused tabs and a wider card grid so configuration controls are easier to find and scan.
- Rebuilt Race Pass so the leaderboard appears first, with challenges, prizes, rules, and history organized into separate tabs.
- Home now greets a driver by name only when a real signed-in account session exists.

## TrackPro V2 2.26.90 - 2026-07-25

- Fixed the spotter repeating himself: a suppression window shorter than the engines' event retention let the same call play again seconds later, which was the largest single source of spotter noise.
- "Next car ahead" now tells you where the car actually is, adding the measured gap to the call instead of only naming the driver.
- Multiclass traffic calls no longer repeat every few seconds in a mixed-class field.
- Corner-trouble warnings ("careful into Turn 7") are limited to twice per corner per session.
- The spotter no longer makes fuel calls before the race goes green, or before the fuel-burn estimate is based on real laps.
- Spotter voices are now the two complete voices, Male and Female; the previous default shipped only a fraction of the phrases, so drivers on it were missing most of what the spotter can say. Existing selections migrate automatically.
- The free spotter gained real controls: chatter level, voice, and per-category switches for traffic, flags, timing, multiclass, fuel, car damage, and engineer chatter.
- Push-to-talk no longer loses a quick re-press while the previous radio turn is finishing.
- Overlays are click-through by default, so an overlay can never sit over the app and block you from changing tabs; installs already affected recover on launch.
- Coach settings: push-to-talk binding moved directly under the microphone settings, and pressing it now starts the coach if it is not already running.

## TrackPro V2 2.26.89 - 2026-07-24

- Rebalanced AI Coach corner cues: roll speed, apex, and exit coaching now lead when they explain the time loss, instead of every corner becoming "brake later"; braking-point cues still speak when they are the whole story.
- Fixed the coach going permanently silent after a guided lap by detecting and reviving a dead voice connection, during and after the walkthrough.
- Guided lap calls now speak in the coach's own voice, pre-synthesized when the lap is armed, instead of the robotic system voice; other dynamic radio lines upgrade to the real voice automatically over time.
- Corner-trouble warnings ("Careful into Turn 7") now come only from the spotter and are limited to two per corner per session.
- Removed the back-to-back repeat of the focus-corner cue right after the start/finish line; the early call now owns the approach.
- The spotter reads your lap time after every valid practice and qualifying lap, in both spotter voices, with a new "Lap time reads" toggle.
- Pressing push-to-talk now starts the coach if it is not already running, and the PTT binding moved directly under the microphone settings with a clear explanation.
- Reduced the frame-rate dip at the start/finish line: onboard recording now uses the GPU's hardware video encoder when available, and finished-lap video processing waits until you are in the pits.
- Haptics can no longer bind to headphones or screen-attached audio outputs, and your shaker selection is remembered even when the amp is powered on after TrackPro starts.
- Quieted the haptics reconnect loop when the output device is disconnected, keeping automatic recovery when it returns.
- Subscriptions now require a real TrackPro account: guests are guided through account creation (Google, Discord, or email) before checkout, and guest mode no longer blocks the sign-in page.
- Fixed a false "OAuth sign in failed" message that could appear even though Google or Discord sign-in succeeded.

## TrackPro V2 2.26.88 - 2026-07-20

- Fixed subscription checkout failures caused by stale Stripe price overrides and made billing errors show their actionable server message.
- Extended the new-subscriber free trial to 30 days and pinned the Supabase client used by billing functions for repeatable Edge deployments.
- Renamed the paid coaching choices to Pro 5× and Pro 20× consistently across the app, Coach, support, and backend responses.
- Reorganized the subscription page so pricing choices appear first in a cleaner, less cluttered layout.

## TrackPro V2 2.26.87 - 2026-07-20

- Unified member, profile, and direct-message avatars around the canonical profile photo, with reliable local initials whenever no image is available.
- Added a one-time repair path for legacy empty profile-avatar rows so older accounts converge without repeated database writes.

## TrackPro V2 2.26.86 - 2026-07-20

- Added targeted database indexes so community lap and Coach reference searches remain fast as telemetry grows.
- Added a privacy- and membership-gated precomputed leaderboard for each track, configuration, and car combination, refreshed every 10 minutes.
- Improved Motion telemetry fidelity with rFactor 2 rotation rates, F1 MotionEx slip data, and an iRacing rear-traction surrogate.
- Strengthened Motion stop and limit handling with gentle parking for normal disable and disconnect flows, while keeping E-STOP immediate, plus expanded safety proof tests.
- Updated the Motion page to follow live profiles, show honest E-STOP state, apply real master gain, and include a hardware rig-testing runbook.

## TrackPro V2 2.26.85 - 2026-07-20

- Improved telemetry gear traces so normal shifts no longer spike through neutral, and expanded surface track maps with sector context.
- Added venue-keyed corner numbers and driving-line fault pins to track maps without tying the display to a specific simulator.
- Added a dedicated Social Events experience with accurate Friday Night Race timing, weekly car/track details, and copyable session information.
- Polished Home and Coach settings with a clearer hardware strip, consistent cards, and toggles that retain their proper shape beside long labels.
- Restored lap coaching across configured OpenAI models, made Driver Profile pace and consistency respond to recent sessions, clearly separated long-term driver traits from single-lap radar labels, and made personal-best comparisons frame the driver's own next-best lap honestly.

## TrackPro V2 2.26.84 - 2026-07-20

- Redesigned the Home page around current season standing, Friday Night Race information, and recent driving sessions.
- Updated Race Pass leaderboards to rank drivers by the XP shown in the interface and made leaderboard rows open the selected racer's profile.
- Improved the first-startup tour so paid pages show their real interfaces as safe, read-only previews while the tour is open, with normal access gates restored immediately afterward.

## TrackPro V2 2.26.83 - 2026-07-20

- Added a guided first-startup tour across TrackPro's main pages, coordinated with the onboard-video consent prompt so startup guidance does not overlap.
- Added a reusable tooltip system and more than fifty contextual explanations across pedals, motion, haptics, telemetry, Coach, and Driver Lab controls.
- Opened Marketplace buying and trading to every account while keeping selling features on paid plans.
- Added Marketplace notifications and email delivery so buyers and sellers do not miss offers, purchases, or direct messages.
- Improved application error recovery with a full Reload App action when a page or dynamically loaded module fails.

## TrackPro V2 2.26.82 - 2026-07-20

- Reworked motion-controller connection so Thanos controllers can be selected, probed, and connected directly from a clearer in-app connection card.
- Motion controller port choices now persist per user and remain stable during the session, with more tolerant FTDI serial-device detection.
- Added a controlled testing gate to the Motion page while the refreshed motion workflow is prepared for wider use.
- Fixed onboard-video consent so the driver's answer is saved before capture state changes and remains correct after restarting TrackPro.
- Redesigned Driver Lab lesson pages with a stronger instructor-led layout and complete, untruncated lesson content.
- Improved Simagic pedal-reactor controls with a real strength slider and removed the inactive polarity control.

## TrackPro V2 2.26.81 - 2026-07-20

- Added the cinematic TrackPro startup experience to every manual launch and Windows auto-start, with the app opening only after the launch sequence is ready.
- Improved AI Coach track awareness, corner honesty, racecraft priorities, earlier teaching, and concise live-radio guidance; Driver Lab now stays on the selected lesson and grades drills from live laps.
- Expanded haptics across iRacing, Assetto Corsa, and ACC with real gear-shift and downshift effects, positional curb feel, wheel-slip lockup feedback, per-game capability indicators, and safer Simagic reactor shutdown behavior.
- Improved Coach and Community voice routing so both use the selected TrackPro headset without duplicate or competing audio.
- Added clearer onboard-video consent and comparison handling, venue visual reference anchors, and more reliable live race and opponent context.
- Improved overlay and borderless-window controls, including monitor-aware sizing and direct Coach control of overlays.

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
