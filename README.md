# TrackPro V2

TrackPro V2 is the Sim Coaches Windows app for sim racers who want one place to set up their hardware, review laps, watch onboard video, compare telemetry, and manage their racing data.

## Download

Download the latest signed installer from the [TrackPro V2 releases page](https://github.com/SimCoaches/TrackProV2/releases/latest).

TrackPro updates are delivered through this public release channel. The app checks the latest release, shows the changelog, downloads the signed installer, applies the update, and restarts.

Latest stable release: TrackPro V2 2.26.181.

Beta [2.26.212](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.212) adds Race mode for the rig's corner LEDs: every flag and the start lights, pit lane and limiter, cars alongside, ABS and TC, a rev bar on the fronts and brake and throttle on the rears, each in its own colour with a Test button per cue; the Native 360 Hz diagnostics tile no longer fails healthy rigs (AI Coach v0.248). Everything in 2.26.211 is included; supervised testing only.

Beta [2.26.211](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.211) makes overlays fit at any display scale with a 50-200% size slider and free placement, makes the FFB overlay's buttons work, fixes the haptics Lo/Hi frequency sliders, and has the AI Coach describe positions from the apex instead of lap distances (AI Coach v0.248). Everything in 2.26.210 is included; supervised testing only.

Beta [2.26.210](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.210) makes the rig move as one rigid body with no diagonal frame twist, adds a live motion monitor on the Motion page, and makes corner LEDs work with Pro Micro boards (AI Coach v0.247). Everything in 2.26.209 is included; supervised testing only.

Beta [2.26.209](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.209) makes the rig lean into banking instead of cancelling it, drops the seat over crests and lifts it in compressions, maps each track's hills and banking and plays them a moment early, adds a Track feel card on the Motion page, and lets you ride along your last lap on the rig (AI Coach v0.247). Everything in 2.26.208 is included; supervised testing only.

Beta [2.26.208](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.208) makes kerb rumble hit hard on the actuators on the side that is on the kerb, gives elevation, suspension and haptics their own share of the stroke, and learns each track's banking and hills so Daytona's banking and big climbs use the travel (AI Coach v0.247). Everything in 2.26.207 is included; supervised testing only.

Beta [2.26.207](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.207) gives kerbs a hard thunk on the side and tyre that hit them, lets actuator haptics play at full strength again, puts track elevation ahead of suspension in the Omega motion tune, drives the rig's corner LEDs without SimHub, lifts shaker kerbs above the engine, and lets Blip run without a microphone (AI Coach v0.247). Everything in 2.26.206 is included; supervised testing only.

Beta [2.26.206](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.206) runs motion tests started from the paired phone at 25% speed (enforced by the PC) and adds the full travel check to the phone, which runs only from Stopped and never leaves motion enabled. Everything in 2.26.205 is included; supervised testing only.

Beta [2.26.205](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.205) starts motion cues up to 3x sooner on every profile (the seat moves about 20 ms after the car's G on a brake stab), adds the Lebois SRT80 control box, an in-app handbrake firmware updater and phone control of every motion setting, lets new PCs drive first and sign up after, and brings AI Coach v0.246: doubled allowances, out-of-talk-time lines in every coach language, and guided "Brake now." calls on time under load. Everything in 2.26.204 is included; supervised testing only.

Beta [2.26.204](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.204) rebuilds Force Feedback around a simple page with an automatic setup check (rotation, force direction, clipping) and car-first effects: shifts are a small knock that cannot pull the wheel, ABS pumps the steering weight, and effects grey out in games that cannot drive them. Haptics outputs recover on their own and name who holds them, and Community gains a support channel. Everything in 2.26.203 is included; supervised testing only.

Beta [2.26.203](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.203) stops TrackPro from disturbing SimHub or FlyPT VR motion compensation while TrackPro motion is off, lets custom games drive the motion platform (Generic Motion Telemetry v1 over UDP), and moves corner calls to iRacing's official turn numbers with Blip's ElevenLabs voices on Eleven v4 (AI Coach v0.245). Custom Spotter voices now come as three distinct takes. Everything in 2.26.202 is included; supervised testing only.

Beta [2.26.202](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.202) keeps League Night results from going missing: result saves retry until they land (even across a restart), a grid-time session no longer records your grid slot, and the server now places drivers whose result never arrived. Google profile pictures load again, and FFB Lab brings lost force back in under a second. Everything in 2.26.201 is included; supervised testing only.

Beta [2.26.201](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.201) makes custom Spotter voices usable in about 7 minutes, builds corner names only for the tracks you race with them on, and updates installed voices by themselves. It also fixes the Blip page flashing a sign-up screen and Navarra's corner numbers (AI Coach v0.244), and adds FFB Lab strength to 60 Nm with an end-stop guard. Everything in 2.26.200 is included; supervised testing only.

Beta [2.26.200](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.200) puts every Spotter Market voice in the Spotter voice menu for everyone and lets Pro 5× and Pro 20× members give Blip any of them (AI Coach v0.243). The Spotter's and Blip's radio clicks now follow their volume, and custom voices follow their description more closely. Everything in 2.26.199 is included; supervised testing only.

Beta [2.26.199](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.199) lets Blip tune your motion rig by voice on track, clear your own black flag in iRacing, and act as your endurance and oval strategist (AI Coach v0.242). The spotter now names the car to follow under caution, and a new motion Anticipation setting (off by default) starts cues from your steering, brake and throttle. Everything in 2.26.198 is included; motion needs rig acceptance; supervised testing only.

Beta [2.26.190](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.190) fixes AI Coach silences after actions and exact spoken volume levels.

Beta [2.26.189](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.189) adds AI Coach evidence, map, fuel and briefing improvements, and the in-game FFB overlay. It includes the 2.26.188 motion changes, which remain on validation hold.

Validation candidate [2.26.188](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.188) contains further motion persistence and controller-protocol corrections. **Supervised testing only; not approved for customer delivery.**

Beta [2.26.187](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.187) is on **validation hold - do not use for customer delivery**. Reliability fixes and physical Thanos4U acceptance are pending.

### What's New in 2.26.181

- Coach PTT preserves slower transcriptions and accepts a held re-key when the previous question finishes.
- Includes recent Coach voice controls and audio improvements, the compact Haptics mixer, and warranty error-message fixes.
- See the [changelog](CHANGELOG.md) for all changes and known limitations. Headset/driving and physical hardware acceptance remain pending.

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
