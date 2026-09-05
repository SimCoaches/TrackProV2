# Changelog

## TrackPro V2 2.26.175 - 2026-09-04 (beta)

- Coach reconnects through its long-session refresh, preserves saved push-to-talk bindings, and handles rapid Stop/Start. Ready and push-to-talk tones are clearer.
- Spotter side and three-wide warnings respond sooner to changing traffic, cancel obsolete calls, and recover from stalled playback and repeated output failures.
- Group Voice adds an optional in-game roster with speaking and mute indicators. Community voice volume and overlapping playback are improved, with new join and leave chimes.
- Wheel Studio adds stop-all LED/dashboard control, persistent off settings, individual LED hardware checks, and better warning-zone coverage. Repeated LED write failures disable the affected transport.
- Native wheel-button capture improves Coach push-to-talk setup. FFB and haptics gain clearer starting profiles and wheel presentation.
- Setup Shop expands NASCAR discovery and matched run comparisons. iRacing capture retains more engineering channels, pit observations, and private saved-setup evidence. Downloadable setup inventory remains a preview.
- Support reports preserve crash history and capture additional evidence for diagnosing unexpected app closure.

Beta testing: verify long-session headset/PTT behavior, rapid NASCAR traffic changes, Group Voice overlays, and physical wheel handover. Hardware and live audio sign-off remain pending.

## TrackPro V2 2.26.174 - 2026-09-04 (beta)

- AI Coach gets a driver-focused home, Live Radio as the primary action, a collapsible Coach Notebook, clearer Driver Progress, and simpler settings.
- Coach answers use richer session history, stricter car/layout matching, faster setup tools, and measured named-driver corner comparisons with clear limits on rival data.
- Motion coordinates all four corners as one chassis plane, refines smoothing and factory tuning, preserves customized profiles, and adds geometry and motion-quality readouts.
- Haptics restores saved outputs without opening its page, retains disconnected devices for reconnection, and strengthens grass/dirt/gravel feedback while keeping quiet tarmac crisp.
- Setup Shop expands its product preview with AI Setup Lab, contribution and personal-proof workflows. Downloadable inventory, community submissions, and rewards are not live in this beta.
- Approved Wheel Studio testers get one-click wheel setup, matching LED/dashboard colorways, improved dashboard defaults, and persistent explicit-off behavior.
- FFB Lab and telemetry reliability improvements are included, along with cleaner diagnostic reporting.

Tonight's testing: check coach microphone/PTT, short spoken answers and HUD-off behavior; begin motion testing at low master gain; verify haptics restoration and off-track feel. Physical hardware and live audio sign-off remain pending.

## TrackPro V2 2.26.173 - 2026-09-03 (beta)
- Coach push-to-talk works again after Stop Coach, and pressing talk while the coach is off starts it and says when it is ready.
- Guided lap tells you it waits for the start/finish line before calling corners.
- Spotter rejoin and pit-exit calls say what to do ("Cars coming behind. Don't pull out yet.").
- FFB Lab settings persist across pages and restarts; a force effect the wheel dropped after a sim exit re-arms itself.
- Assetto Corsa no longer floods the app window with 333 Hz telemetry (the cause of most frozen-UI reports).
- Pedal haptics panels keep their labels at narrow window widths.
- Warranty claims accept phone videos (MOV, MP4) up to 100 MB.

## TrackPro V2 2.26.172 - 2026-09-02 (beta)

- Fanatec ClubSport Pedals V3 rumble works again when TrackPro is processing the pedals: the pedals are hidden from other programs by design, and TrackPro's own rumble writer was hidden with them. The app now sees and drives the pedal motors.
- The coach gives corner targets the way a race engineer would: the number to aim for and how sure it is, in plain words. No system vocabulary on the radio.

## TrackPro V2 2.26.170 - 2026-09-02 (beta)

- The coach knows reference corner speeds before your first lap, learned from the community's fast laps across cars and tracks and scaled to your car; on a layout nobody has driven it gives a rough target from the track's shape, spoken as a range. All of it is labeled as an estimate and confirmed against your own passes.
- iRacing depth: the sim's live delta, in-car dials, shift lights, set tire pressures, track wetness and driver rating are in the coach's context; sector deltas and the optimal lap are in the Timing block; practice corner answers go deeper, car-state questions route to car data, repeats and positive-feedback questions get straight answers.
- Damage, fuel, laps left and time left answer instantly in the coach's own voice with the sim's numbers.
- A question the link dropped is replayed after the reconnect; stale telemetry says so instead of refusing; offline iRacing test sessions no longer read as one lap to green.
- Fastest-lap comparisons name corners from the validated map; lap times keep milliseconds and gaps stay in tenths.
- Assetto Corsa Competizione saves the whole first flying lap of a stint, not a 0.75 s tail.
- Telemetry laps are stored as compressed per-lap records with a local lap store; reads and corner passes are faster and complete.
- Welcome flow: coach voice matches the radio check, checkout back path, trial state, colorway resume, headset hydration, pending email and language rows fixed.

## TrackPro V2 2.26.169 - 2026-09-02 (beta)

- Headset setup pairs the mic and headphones by hardware and never hides a headset whose output Windows names "Speakers (...)"; the pickers pre-fill from the device Windows already uses for calls, monitors and TVs stay hidden behind a "show all outputs" link, and one Radio check button replaces three.
- The coach's own voice now plays for every cue clip: the client read the TTS reply as text and threw, so every phrase fell to the Windows voice. The shared clip library (15,396 clips across six voices, plus 12,420 named-corner clips) now exists in production, and guided-lap phrases are voiced at session start.
- A guided lap arms with its clips ready, fills in reference marks that arrive before the start line, says plainly when no reference exists yet, and setup cues never use the robotic engine.
- Interrupted coach audio that the server never confirmed cleared used to disconnect the coach for the rest of the session; it now heals in place.
- New paid Brake Approach overlay: two arrows close on your reference brake point and meet at it, then show how many meters early or late you braked; turn-in follows. Opens with a guided lap. Coach Cue, Race Engineer and Brake Approach unlock on the Starter plan; free members see them greyed out.
- Corner references use the laps of the session being driven the moment they complete, not after the save.
- The Overlays page warns when the sim is in exclusive full screen, and the welcome radio check reports whether the personal line played.

## TrackPro V2 2.26.168 - 2026-09-02 (beta)

- Suspension and kerb strikes are scaled per sim. One threshold for every 60 Hz sim made Assetto Corsa fire a full-force thump on every transition of a drift while ACC never fired at all; each sim now gets its own scale (AC 3.0 m/s, ACC 1.5, Le Mans Ultimate 0.9, iRacing 4.0 on its 360 Hz data).
- The shaker output path is chosen automatically. "Automatic" dedicates a real amp output for the fastest path and leaves the Windows default device shared so everything else keeps playing; "Dedicated" and "Shared" remain as overrides. The page now says when game audio reaches the shakers on a shared default output.
- Assetto Corsa sessions no longer split on a hiccup: the sim must be missing from three consecutive process checks before it is declared gone, the process snapshot retries, and a telemetry stall closes the session only after thirty seconds.
- Haptics profile changes from a slider drag are sent once every 60 ms instead of fifteen times a second, so a drag cannot starve the audio callback.
- Staff log pulls now carry the whole rolling log.

## TrackPro V2 2.26.167 - 2026-09-02 (beta)

- Drifting no longer drones. On sims with a real slip channel the wheel-slip scrub strikes when a slide begins and fades to a simmer while it lasts, striking again on a fresh transition, instead of holding at full for as long as the car is sideways.
- "Shakers only" (exclusive) output heals itself. The render loop now notices when a 3 ms period is being missed under sim load (the hardware replays stale audio, heard as a random rumble), counts it, and steps the period up to 6 ms and then 12 ms on its own.
- Fleet noise: startup races with the engine, network failures and the auth lock steal between TrackPro windows are no longer recorded as errors; Discord alerts describe the last 24 hours and only repeat when something grows.

## TrackPro V2 2.26.166 - 2026-09-02 (beta)

- TrackPro now says why telemetry is not flowing. When a sim is detected but has not connected for fifteen seconds, or a sim is running as administrator where TrackPro cannot see it, an amber notice appears at the top of the app with the fix in plain words, and withdraws itself the moment the sim connects. The same condition reaches the fleet as a structured event and a Discord warning, once per rig per six hours.

## TrackPro V2 2.26.165 - 2026-09-02 (beta)

- Switching from iRacing to another sim works again without restarting TrackPro. iRacing's shared memory outlives the sim (its UI keeps it open), and the game detector took its presence as proof iRacing was running, so it never looked at Assetto Corsa: no telemetry, laps, coach or haptics after a switch. iRacing now claims detection only when its data is actually live.
- The haptics output picker no longer offers a monitor's HDMI audio. Core has always refused screen-attached audio, but the picker's own rule did not, so a driver could "select" a monitor and get silence with no explanation.
- The Haptics page says "No sim telemetry" when TrackPro is not receiving the game, instead of "Waiting for the car to roll".

## TrackPro V2 2.26.164 - 2026-09-01 (beta)

- The coach never answers a press that carried no speech. A dead or muted mic gets "Say again? I got no audio" in the coach's own voice instead of improvised coaching, and the dead-mic warning comes on the second silent press.
- The hot post-lap questions ("how was that lap", "where am I losing time", "what should I work on", "what lap am I on") are pre-rendered at the line and played in the coach's own voice with no model round trip, about a second sooner.
- Suggestions per lap replaces Coach Chatter: 1, 2 or 3 per lap, default 2, one slot always kept for the focus corner. The old buttons wrote a setting the cue engine never read.
- Pre-race stop planner: "how many stops for a 40-lap race" answers with box laps, fuel to start and per stop, and the stop cost measured from your own in-lap and out-lap. Caution stops, drive-throughs and garage dwells never price a stop. On iRacing the usable tank comes from the session's fuel rules.
- Trace-shape corner reads against your session-best pass: where the time went in metres from the apex, and what the brake and throttle traces did differently.
- Live per-corner delta booked at every corner exit, this lap and last, with the reference labelled (own best, community best, or session best).
- iRacing: per-wheel brake pressure measured under straight-line braking and compared with the bias dial when the car has one; damper high-speed share, kerb and bump strikes, and travel in the engineer block.
- Driver-induced slides name the corner and the technique behind them.

## TrackPro V2 2.26.163 - 2026-09-01 (beta)

- Haptics synthesis audit. The sine wave every effect is built from was lopsided (its negative half peaked at two thirds), so every tonal effect carried a DC bias and a second-harmonic buzz. Fixed. Engine pitch now rises continuously with revs instead of dropping an octave twice up the range, and the engine is felt harder as revs climb and under load. ABS pulses now sit in a band a bass shaker can reproduce. A kerb strikes once, not again on exit. Suspension thumps decay as advertised. Impacts no longer go silent for their last third. Kerb and bump thresholds reach ACC and Le Mans Ultimate as intended. Measured on a staff lap: engine DC offset gone, engine loudness correlation with revs from -0.35 to +0.57.
- Saved profiles get the "New feel available" offer again, because the ABS band changed meaning (pulses per second x carrier Hz).

## TrackPro V2 2.26.162 - 2026-09-01 (beta)

- Fixes 2.26.161 on onboard sound cards: the haptics output no longer closes and reopens every half minute. The low-latency probe's normal "no faster period here" answer was being treated as the stream dying, so the working stream was torn down and rebuilt in a loop and the seat cut out each time. Seen on a staff rig within the hour of install; a refusal before the stream starts is now never a death.
- If a change on the Haptics page cannot reach core, that failure is recorded in the diagnostics trail instead of vanishing.
- The live meter never competes with the audio callback for the mixer (a lost race was ten milliseconds of silence). Fleet haptics reports (latency, endpoint reach, dropped callbacks) ship correctly again, and two long-repeating warnings dedupe.

## TrackPro V2 2.26.161 - 2026-09-01 (beta)

- The Haptics page shows what is shaking the seat: a live meter on every effect, the priority chip that is holding a slot lights up, and the Engine row names the engine the firing order is following ("V8", "Four-cylinder", or "car not recognised, assuming six").
- Engine vibration is the engine's firing order - a four knocks, a V8 hums, a V10 sings - felt hardest under load and easing at redline, instead of a tone that follows the tachometer. Lateral load marks turn-in and weight transfer instead of droning through every corner. Kerbs and bumps now fire on Assetto Corsa, ACC and Le Mans Ultimate, where the old thresholds were tuned to iRacing's 360 Hz data and never triggered. Wheel slip sustains through a real slide on sims with a real slip channel. Road texture is audible.
- A fresh profile starts with the eight effects that carry a lap and three priorities, not twelve and six. Saved profiles get a one-time "New feel available" offer on the Haptics page and are never changed without a click.
- Haptics can play through up to four audio devices at once, sixteen shakers total. Add devices under Channels; every shaker becomes its own zone with a mount preset (Seat left, Pedals, Backrest, Front left...) and a name. Channel numbering stays fixed when a device is off.
- The output pill shows the latency an output can reach before a stream opens, "No amp output found" says what to do, and Priority is hidden on effects that are switched off.

## TrackPro V2 2.26.160 - 2026-09-01 (beta)

- Prestige is something other drivers can see. Your crown now appears beside your name everywhere you show up - the members rail, community chat, direct messages, the driver browser, friends, and the Race Pass leaderboard - instead of sitting on your own profile where only you could find it.
- Each prestige earns a different crown, not the same one in a new colour: steel at Prestige I, solid gold with a ring around your avatar at II, a crown that moves at III, and a prismatic crown with your name in its own colour at IV. Previously every prestige past the first drew an identical crown.
- The members rail shows the crown your next prestige unlocks, and says what it does, so the reward is visible before you earn it rather than discovered afterwards.
- Prestiging swaps your crown immediately. It used to keep showing the old one for up to two minutes.

## TrackPro V2 2.26.159 - 2026-09-01 (beta)

- A sim launched as administrator (Content Manager's "Run as administrator" is the common way) was invisible to TrackPro: no telemetry, no laps, no coach, no haptics, and the community rail showed you as merely online while you were driving. TrackPro now identifies running games without needing permission over them, so an elevated sim behaves like any other.
- When a sim really is unreachable, TrackPro says so: Assetto Corsa clearly running but with no visible process now appears in the logs with the likely reason, instead of looking identical to never having opened a sim.

## TrackPro V2 2.26.158 - 2026-08-31 (beta)

- On the beta channel, a new beta comes to you: a green Install Beta button with download progress and an automatic restart - the same one-click experience stable users get, in green so you always know you are taking a test build. No more hunting through Settings for the right version. A stable release still wins the screen if both are waiting.
- Event Mode has a master switch in Settings. Turning it on binds TCP 5001, broadcasts on UDP 5001 and 5003, and runs the automatic lap sender, which fought any rig using a standalone lap-time sender with no way to opt out. Off means off: TrackPro holds none of those ports and sends no laps. Defaults to on, so a rig already running events is unaffected.
- The coach speaks and listens in the language saved on your account.
- Everything in the 2.26.157 beta is included (dedicated shaker output at 3ms, ranked haptic priority, four corners plus a seat, and the launch fix).

## TrackPro V2 2.26.157 - 2026-08-31 (beta)

- Give the shakers an output of their own and they run on a 3ms path instead of a 10ms one. A Shared / Shakers only switch sits beside the output picker on the Haptics page and shows the delay you actually got - 3.0ms means it worked. Windows will not hand over a device that is already playing something else, so point it at an output nothing else uses; your amp and shakers do not change.
- Priority is an order, not a checkbox. The Haptics page shows the order and lets you move effects up and down: the top two hit at full strength and push everything else down while they land. Setting half your effects to Priority used to mean none of them won; the page now says how many are set and how many can fire.
- Four corners plus a seat, and zones you define yourself, with a level for every effect into every shaker - so braking can live at the front corners and the engine in the seat instead of twelve effects sharing two shakers. Existing rigs are unchanged until you route them.
- Haptics stay quiet when you are not in the car: entering and leaving an iRacing session no longer shakes the rig.
- Audio interfaces (MOTU, Behringer, PreSonus, RME, Audient and others) now appear in the haptics output list instead of being filtered out.
- TrackPro measures its own haptic delay end to end, and records what each of your outputs is capable of.
- Fixed a blank screen on launch present in the unpublished 2.26.156 build; no released version was affected.
- Coach: radio volume, greeting and ACC session length fixes, and track length is measured from a lap when the sim never reports one.

## TrackPro V2 2.26.156 - 2026-08-30 (beta)

- Pit strategy answers where you come out, not just when to stop: a stop costs your own measured pit loss, so the coach names the cars you would rejoin among and whether that slot is clean air or a train. Cars already in the pits are excluded, and an unmeasured pit loss projects nothing rather than inventing a pit-lane time.
- Traffic answers when, not just who: how long until you reach the car ahead and until the car behind reaches you, from measured pace on both sides. The out-lap after a stop is included and given as a floor - the real one is slower - unless your own cold-tire penalty has been measured.
- The coach compares your lap against the fastest lap in the database for that exact car and track, corner by corner, instead of only your own best. Seeing other drivers' laps still requires sharing your own; if sharing is off he says so and can turn it on mid-conversation. The reference driver is never named.
- The questions asked most - how was that lap, where am I losing time, what should I work on - are answered in one hop from what the coach already measured, with no tool lookup.
- The coach carries only the tools that fit the sim you are in, and warms his connection before you speak.
- Long comparison reads are bounded, so a slow lookup can no longer leave the coach silent mid-answer.

## TrackPro V2 2.26.155 - 2026-08-30 (beta)

- Ask the coach for any lap in plain words: "analyze lap 32 from Monza last week", "my fastest lap at Summit Point in the Miata ever" - track words, car words, dates, and all-time scope all resolve; a numbered lap missing from the latest session is found in older ones automatically, and every answer names the session it used (track + date) so a wrong pick is one correction away.
- Coach answers land faster: candidate laps fetch in one batched query instead of one-per-session, both laps' telemetry loads in parallel, the hardware readout probes all four subsystems at once, and friend comparison plus hardware reads join the pre-start lane (their work overlaps the coach's own speech).

## TrackPro V2 2.26.154 - 2026-08-30 (beta)

- Open mic (beta toggle, off by default): just talk to the coach - no key needed. The adaptive voice gate (the same engine behind Community Voice) opens transmission when you speak and closes on silence; the coach never listens while he's talking, your talk key still works and always wins, and a stuck-open mic force-closes after 30 seconds.
- Ask the coach "what's my wheel rotation?" and get a measured answer: he tracks the largest steering angle you actually use each session - a hard lower bound on the configured rotation - instead of saying he can't read it.

## TrackPro V2 2.26.153 - 2026-08-30 (beta)

- The coach fixes your connection instead of shrugging: when telemetry is missing he diagnoses WHY and speaks the exact fix for your sim (F1 games: UDP telemetry on, port 20777; BeamNG: OutGauge on, port 4444; iRacing/AC/ACC/rF2/LMU: run the game on this PC in a session). "Telemetry isn't connected" as a dead end is gone.
- The coach analyzes laps you already drove - parked, off-sim, no game running: "analyze lap 32" or "how was my race last night" pulls the stored lap from your account, compares it against your best clean lap of that session, and names the corners where the time went. Being told "I need live telemetry" for a lap that's already saved is gone.
- Corner numbers verified against physics fleet-wide: every active track's turn map was checked against measured driving data. Four tracks had every label rotated (Sachsenring, Navarra, St. Petersburg, Portland) - all fixed from real telemetry; Sachsenring additionally gets hand-measured corner spans.
- Spoken names drop iRacing's disambiguation digits ("Robinson", not "Robinson2").
- Coach tool timing is now measured per tool in the rolling logs, so slow answers are diagnosable by name.

## TrackPro V2 2.26.152 - 2026-08-30 (beta)

- The spotter says driver names: "Next car is Robinson", fastest-lap calls with who and the time, pit calls, watched rivals - names with no recorded clip are spoken dynamically instead of silently dropped, and frequent phrases upgrade to the coach's real voice. Dynamic speech turns on for everyone once (an old default was muting names, exact lap times, and fuel figures); switching it off afterwards is respected.

## TrackPro V2 2.26.151 - 2026-08-29 (beta)

- Spotter reflexes: car left / car right / three-wide fire the instant the overlap appears (~30-50ms, faster than CrewChief) - a redundant onset debounce and the engine-tick wait are gone. Clears, flicker damping, and mid-corner clear holds are unchanged.

## TrackPro V2 2.26.150 - 2026-08-29 (beta)

- Sim frame drops at lap end addressed: all post-lap onboard video work (encode, trim, concat, probes) runs at Windows IDLE priority and software encoding is capped at two threads, so lap-boundary video jobs can no longer steal frames from the sim. Rigs without a working hardware encoder now say so in shipped diagnostics.

## TrackPro V2 2.26.149 - 2026-08-29 (beta)

- Lap replays load frames in parallel with an honest retry state when the server is momentarily busy (read-side companion to .148's save retry).
- Telemetry frames persist at a uniform 60Hz across every sim for like-for-like lap comparisons.

## TrackPro V2 2.26.148 - 2026-08-29 (beta)

- League race results capture at the final classification, not when the first car takes the flag - Friday's Week 2 standings froze mid-final-lap and have been corrected to the official finish.
- Lap saves ride through momentary database congestion (retry-in-place) instead of failing and re-uploading minutes later - hardening from Friday League Night field data; no lap data was lost.
- The community members list is fetched once and shared across surfaces, roughly halving background database traffic on Home.

## TrackPro V2 2.26.147 - 2026-08-28 (beta)

- Review hardening for the social update: the Social chat badge now clears on visiting busy channels and accrues while the app is minimized; League Night join credentials are database-enforced for signed-out clients; "on track" status clears sooner and never carries across accounts; chat sends can't duplicate; YouTube links with trailing punctuation embed; trial-offer analytics no longer double-count; friendly names reach the in-game overlay and Haptics; less background polling.

## TrackPro V2 2.26.146 - 2026-08-28 (beta)

- On-track status is steady: iRacing pausing its telemetry feed (garage, replays, session changes) no longer makes drivers pop on and off the online list several times a minute. Status holds through short gaps and clears after a real exit; offline and voice status still clear instantly.

## TrackPro V2 2.26.145 - 2026-08-28 (beta)

- The real community chat lives on Home: read #general and post to it right from the dashboard, live.
- Chat notifications: the sidebar Social badge counts channel messages you haven't seen (plus unread DMs); reading a channel clears it instantly.
- YouTube links in channel chat, DMs, and the Home chat play inline (click the preview to watch).
- League Night shows for signed-out visitors as a reason to join; session credentials appear once you have an account.
- The online members bar shows every online driver - no more "+N" overflow chip.
- The coach is referred to as "he" across the app.

## TrackPro V2 2.26.144 - 2026-08-28 (beta)

- Home rebuilt around coach, league, Race Pass and live community: a "Happening Now" strip shows who is on track right this second, the Race Pass card names your season rival and the exact XP gap, and free drivers see the 30-day trial (with the measured coaching improvement number) instead of a price banner. Signed-out drivers get the trial pitch with a one-click path to signup.
- Removed from Home: hardware status strip, quick actions, and recent activity (all live elsewhere).

## TrackPro V2 2.26.143 - 2026-08-28 (beta)

- Track and car names are now real names everywhere sessions are listed (Home, Insights, Telemetry, Profile): Assetto Corsa content ids like "ac_legends_ta_firebird_1970" read "AC Legends TA Firebird 1970".
- The AI Coach card on Home shows your best lap with the improvement next to it, the coach's focus for tonight, and a "Drive with your coach" button.
- Installing a build from the in-app Beta Channel now shows live download progress.

## TrackPro V2 2.26.142 - 2026-08-28 (beta)

- Haptics flight recorder: every five seconds the rolling logs record the peak level each haptic effect actually rendered, by name. "The seat vibrated and I don't know why" is now answerable directly from logs — which effect, how hard, and when — instead of reverse-engineering lap telemetry.
- Includes all 2.26.141 fixes below.

## TrackPro V2 2.26.141 - 2026-08-28 (beta)

- Phantom impact thumps while drifting are gone (second report, and this time the fix is built from the reporter's own lap data, not desk math). Two real causes, two gates: (1) a hard drift flick swings lateral G far faster than any "crash-only" threshold — on sims with a real slip channel (AC, ACC, rFactor 2), an established slide now suppresses the G-spike impact arms entirely; (2) aggressive downshifts and clutch kicks on the straight shunt the driveline hard enough to read as a frontal hit with the brake untouched — the frontal-impact arm now requires the wall to actually eat speed. iRacing's estimated slip channel keeps today's behavior. Trade-off: a genuine wall kiss mid-slide no longer thumps on real-slip sims.
- Impact triggers are field-diagnosable: every live Impact/Collision trigger logs its arm, G-jolt, and slip into the rolling logs, so a false-fire report is answerable from logs instead of lap forensics.
- Laps stuck mid-upload recover on the next launch instead of staying ungraded forever (found in the field: a driver raced three weeks with laps silently not reaching the server). When telemetry is live but laps repeatedly fail to save, a visible warning says so instead of staying silent.
- Assetto Corsa lap capture survives pauses and session restarts - modded-content sessions no longer churn into zero-length sessions that lose every lap.

## TrackPro V2 2.26.140 - 2026-08-28 (beta)

- Instant coach lines (beta toggle, off by default): cues, verdicts, openers and debriefs play from the coach's cached voice for near-instant starts; questions stay on his live voice. Applies live to the running coach.
- Human-reviewed track craft at fifteen circuits (all League season tracks included) plus MX-5 Cup and GT3 car behavior — the coach explains the "why" behind measured coaching and never invents knowledge on unreviewed tracks.
- My Program rebuilt to proof-first: a measured coached-vs-uncoached improvement strip, the climb graph, and the single thing to work on.
- Talk discoverability: the opener names the driver's actual talk key, Start Coach nudges once when on track without the coach, and the coach overlay gains live status with a start/stop control.
- Community Voice keeps full volume during coach speech by default; the ducking dip is opt-in and saved levels are preserved.
- Per-driver ask-response learning: numeric asks are graded against how much the driver applied, feeding the what-works profile.
## TrackPro V2 2.26.139 - 2026-08-27 (beta)

- Total-reliability diagnostics: every install ships its complete rolling logs automatically (5 minutes after launch, then every 30 minutes) â€” compressed, size-capped, indexed, and scrubbed of tokens/passwords/keys/payment references before leaving the machine. Field issues become diagnosable from our side without asking anyone for files; the whole system dials back remotely.
- Silent haptic Tests self-report: a Test that renders no signal logs a warning, and warnings ship within 30 seconds â€” dead Test buttons anywhere in the fleet are visible without a bug report.

## TrackPro V2 2.26.138 - 2026-08-27 (beta)

- Haptics Test buttons hardened further: Test now bypasses spatial channel routing entirely (spatial gains come from live driving data a bench test doesn't have), so every active output plays every test on every layout â€” guarded by a new all-effects Ã— all-layouts test.
- Test demos louder: guaranteed minimum test level raised 55% â†’ 70%.
- Every finished test logs the exact signal level it rendered, so a dead-feeling Test button is now diagnosable from one core-log line (no signal vs downstream device/wiring).

## TrackPro V2 2.26.137 - 2026-08-27 (beta)

- Dog-box gear shift is ONE clunk now. A real dog box has no synchros â€” the dogs clunk once when they come together (confirmed by a dog-box driver). Previous builds modeled a second hit ~40ms after the first, which read as a double thud. Single strong, sharp clunk; the retune's extra strength and crack stay.
- Fanatec V3 rumble motor floor is rig-tunable (fanatec_erm_floor in haptic-feel-tuning.json) so the little motors' response point can be dialed from real-hardware feedback without a rebuild.

## TrackPro V2 2.26.136 - 2026-08-26 (beta)

- Pedal haptics moved to the Pedals page, under each pedal â€” the same spot as the Simagic reactor controls. The Haptics page is back to seat/chassis shakers only.
- The pedal haptics section auto-detects hardware: V3 pedals â†’ V3 rumble controls only; Simagic reactor â†’ Simagic panel only; both (V3s upgraded with Simagic pucks) â†’ a small picker, defaulting to the V3s; neither â†’ one quiet line.
- Per-effect strength sliders for V3 rumble â€” each effect gets its own level on top of the per-pedal strength.
- Tuned for the V3's motors: intensities map into the little gamepad-style motors' real response band (below ~a fifth of drive they don't spin at all â€” subtle effects used to vanish there). Off stays perfectly off.

## TrackPro V2 2.26.135 - 2026-08-26 (beta)

- NEW: Pedal rumble for Fanatec ClubSport Pedals V3 â€” the vibration motors in the throttle and brake pedals now work in TrackPro. ABS pulse and lockup grind through the brake; wheelspin, gear-shift kick, and downshift rev-match through the throttle. Pedal Rumble card at the bottom of the Haptics page: enable, per-pedal strength, effect picks, and per-pedal Test buttons that work with no game running.
- Supports pedals connected directly by USB; pedals plugged into a Fanatec wheel base can be driven through the base with the experimental wheel-base option (verified on CSL Elite bases, best-effort on DD/other bases).
- Same safety discipline as the Simagic reactor support: motors force-stop if the app dies or telemetry stalls, exact-device matching only, and no USB traffic at all when the pedals aren't present.

## TrackPro V2 2.26.134 - 2026-08-26 (beta)

- Every haptic Test button now makes noise: Test plays the full demo even when the effect is toggled off or its volume slider is at zero, then restores your saved settings. A disabled effect used to test as dead silence.
- Lockup / Flat Spot is audible for the first time: a gain-staging bug had the brake-lockup grind rendering at ~1/100th of its intended level everywhere â€” in game and on Test. Check its volume against your other effects.
- Gear shifts feel like a dog box: two mechanical hits per shift (dog ring slam, then the driveline lash shunt), ~30% stronger with a sharper crack. Downshift rev-match punch scaled to keep downshifts on top.
- Fixed random strong rumbles while driving hard (reported in Assetto Corsa): the crash-impact effect could false-trigger on aggressive drift transitions and hard brake stomps. The detector now separates tire-limited driving from genuine contact (wheel slip tells a barrier scrape from a drift); real wall taps still thump.

## TrackPro V2 2.26.133 - 2026-08-26 (beta)

- Warranty return shipping handled in-app: when your repair is done you get an email, pick a carrier in TrackPro â†’ Support â†’ Warranty, and pay right there â€” we ship the moment it's paid, with live tracking. Parts and labor stay fully covered; shipping is the only cost either way (Warranty+ keeps free overnight both ways).
- Warranty shipping robustness: spelled-out state names no longer break labels, abandoned payment sessions expire in 30 minutes, stale payments auto-refund, and a shipped box advances the claim from carrier tracking even without a button click.
- Beta Channel members get a notification when a new beta is available, with a View button to the version list. Nothing installs without your click; each beta notifies once.

## TrackPro V2 2.26.132 - 2026-08-26 (beta)

- NEW: Beta Channel in Settings â€” opt in to see the recent version list with recommended / testing / buggy tags, one-click install for newer builds, and installer links for older ones (signed and verified like stable; nothing installs automatically; the next stable release returns you to the main channel).
- Mono haptics now drive BOTH shakers: the mono layout previously output on one channel, leaving the second shaker of a standard kit silent.
- Kit tuning matched to real hardware: frequency bands at the Dayton datasheet limits for BST-1/BST-300EX, power ceilings derived from the shipped amps. The 100W kit was throttled to roughly half its safe output and now delivers noticeably more.
- Haptics page honesty: F1 wheel-slip effects note they need F1 23+ with the MotionEx UDP packet enabled.

## TrackPro V2 2.26.131 - 2026-08-26 (beta)

- No more thud when first getting in the game: haptics used to jump from silence to the full effect bed in one sample when telemetry went live. Effects now ease in over ~120ms at session join and fade out when telemetry stops, instead of cutting.
- The always-alive road feel is back: a reduced version of the classic speed bed now runs under the real-waveform texture playback, so smooth roads breathe with speed again while kerbs and surface events still play their true signature on top.

## TrackPro V2 2.26.130 - 2026-08-26 (beta)

- Assetto Corsa / ACC haptics feel restored: the Aug 14 move to high-rate telemetry polling silently changed the change-rate math behind impact, slip and kerb triggers (noise amplified ~5x, impacts over-clamped in response, split-second events droppable). Rates are now computed over a fixed window that behaves identically at any telemetry rate; all effect tuning keeps its original meaning.
- Wall taps and scrapes thump again, including a new side-contact trigger â€” a lateral jolt with loaded tires (the drift wall kiss) now fires the impact thud. Side contact never had its own trigger before.
- Coach settings changed by voice no longer display stale or get silently reverted by the Coach page's next save.
- Motion controller type survives a core engine restart; FFB Lab's Invert switch shows the engine's real state after a restart.

## TrackPro V2 2.26.129 - 2026-08-26 (beta)

- FFB Lab survives session changes: practice to qualifying to race no longer needs a lab restart. A dead force connection is detected, reconnected automatically, and force ramps back in from zero â€” never resuming mid-corner at full torque.
- FFB effects (engine rumble, shift knock, ABS, slip, bumps) now scale with steering load so they stay feelable mid-corner instead of vanishing as you turn in; total effect contribution stays hard-bounded. Shift knock leads with the hit like a real driveline jolt.
- FFB in every game: fixed inverted steering torque on rFactor 2 / Le Mans Ultimate (the wheel pushed into corners); F1 games and BeamNG now get synthesized force feedback built from steering and lateral G, labeled as synthesized on the lab page.
- New end-stop safety guard for all games and wheel bases: the lab learns which way torque moves your wheel and automatically cuts force if output keeps driving the rim into its end stop (the signature of a flipped sign anywhere in the chain).
- iRacing: the FFB Lab stands down automatically while iRacing's own force feedback is enabled â€” two force sources never fight over one wheel.
- Crash protection now logs every trip with the G reading that caused it.

## TrackPro V2 2.26.128 - 2026-08-26 (beta)

- Hard THUD on gear shifts and kerb strikes: continuous effects momentarily duck out of the way while an impact fires, so the hit owns the full shaker stroke. The punch was being masked, not missing.
- ACC and Assetto Corsa road/kerb texture now plays the car's real suspension waveform (the same high-rate playback iRacing got) instead of synthesized noise.
- SIMAGIC P-HPR: the streaming path now uses the same output-route discovery as the Test button, so boards that only answer a fallback route work while driving.
- Motion settings and the enabled state survive an app restart: the saved profile loads at startup, and if motion was enabled when you closed TrackPro it re-arms on launch (waiting for telemetry behind the full safety chain; an emergency stop always cancels the re-arm).
- Motion page shows a live command-smoothness readout to separate software jitter from controller-side settings.

## TrackPro V2 2.26.127 - 2026-08-26 (beta)

- Fixed high CPU usage while pedal haptics were active â€” severe enough on some rigs to cause stutter or disconnects in iRacing. The SIMAGIC P-HPR writer now sends motor state only when it actually changes (with a once-per-second refresh; the feel is unchanged), and the bass-shaker audio stream uses a shaker-appropriate buffer size instead of an aggressively small one some audio drivers service expensively.

## TrackPro V2 2.26.126 - 2026-08-26 (beta)

- Driver Lab is now early access behind an access code while the course videos are in production. Existing progress is untouched; ask the Sim Coaches team for access.

## TrackPro V2 2.26.125 - 2026-08-25 (beta)

- NEW: Report Card (Racing > Report Card). Your last 30 days, measured from your own driving: time the AI Coach found you on coached corners, your improvement rate on coached vs uncoached corners, your community pace-group climb, habits fixed or fading vs still recurring, seat time, and the one thing most worth working on next. Every number is real; sections say honestly when there is not enough data yet.
- Returning accounts skip setup: if you finished account setup once, signing in on a new PC no longer re-walks the setup screens â€” at most you see the final plan screen once. Signed-out machines still offer account creation as before.

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
- Fixed the first callout of a session coming out as a robotic computer voice â€” the coach's real voice clips are warmed before connect.
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

- Fixed third-party pedal axes being zeroed during report silence â€” including a throttle held flat against its stop. TrackPro now holds the last known pedal state while the device connection is verifiably healthy; real disconnects are detected instantly from the failed read, and a frozen device is caught by a direct liveness probe within seconds.
- Beta: game-controller buttons (push-to-talk, hotkeys) are read directly from the HID layer with persistent device handles, replacing legacy Windows joystick polling and eliminating a Windows-level registry-handle leak on rigs with frequently changing USB devices. Beta builds are published as pre-releases and are not delivered by automatic update.

## TrackPro V2 2.26.115 - 2026-08-15 (private beta, superseded by 2.26.116)

- Earlier beta of the HID-native button reading; its pedal-silence handling was incomplete and is replaced in 2.26.116.

## TrackPro V2 2.26.114 - 2026-08-15

- Fixed third-party pedals (including Fanatec ClubSport V3) showing as disconnected and reconnecting in a loop whenever they sat idle: pedals that only send data when moved were treated as unplugged after three quiet seconds. TrackPro now verifies the connection directly and leaves a healthy idle device alone.
- Fixed two startup crashes on PCs where TrackPro launches within the first minute after Windows boots.
- Fixed a background loop that re-scanned all USB devices every second when a configured haptic device was absent, and cut game-controller polling by ~95% â€” both could interfere with streaming pedals on USB-heavy rigs.
- Diagnostic recording no longer amplifies disk writes during device error bursts.

## TrackPro V2 2.26.113 - 2026-08-15

- Fixed third-party pedals (including Fanatec ClubSport V3) dropping out and centering mid-corner. Background device discovery re-walked the whole device tree every two seconds, which on USB-heavy rigs could starve pedal reads for 5-12 seconds. Detection is now push-based â€” Windows notifies TrackPro the moment hardware changes â€” cutting background device walks by over 99% while making hot-plug response faster.
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

- The setup flow's headset step now handles a headset plugged in late: it explains that no microphone was found, watches for one, and continues by itself the moment Windows sees it â€” no more raw "Requested device not found" dead end.
- A remembered microphone that's no longer present falls back to the system default instead of a dead level meter.

## TrackPro V2 2.26.106 - 2026-08-11

- Fixed onboard recording restarting itself every two seconds on untimed laps (out-laps, tows): recordings now survive, and the constant background CPU and disk churn it caused is gone.
- The collapsed members rail now shows every online driver's picture (up to twelve, then a +N counter) instead of only the first four.
- Dash Studio layouts now render on the wheel's own screen (VoCore-based displays), and Moza and Fanatec wheels join device discovery.

## TrackPro V2 2.26.105 - 2026-08-11

- One-time driver setup now belongs to each account: signing in on a PC where someone else already finished setup no longer skips yours, and signing in mid-session routes you into setup if yours was never finished.
- Fixed shared-PC settings bleed: a newly signed-in account can no longer inherit another driver's coach and spotter settings.
- The final setup screen can no longer be missed by closing the app right after the radio check â€” setup resumes there on the next launch.
- Fixed ACC lap saving: laps driven in Assetto Corsa Competizione are now captured and saved (on-track detection previously discarded every ACC lap).
- Race Pass now shows a full XP history â€” every award this season with time, description, and +XP, grouped by day.
- Race Pass tiers continue past 100: Elite tiers progress at 2.5x XP cost, with tiers 1-100 and all rewards unchanged.
- The "active on another PC" screen now appears only when TrackPro is actually running on another PC; a claim left behind by a closed app is taken over silently.
- The sign-in page got the welcome-flow treatment: your coach is on the left of the screen, waiting with the radio.
- Fixed drivers dropping to offline or "went dark" mid-session: TrackPro minimized behind the sim no longer throttles its own heartbeats, and noisy diagnostics can no longer drown them out â€” Online and On-track status now hold through multi-hour stints.

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
- Normal app shutdowns are now delivered immediately to fleet diagnostics, reducing false â€œwent darkâ€ incidents when a driver closes TrackPro normally.
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
- Sim Center: introduced Driver Cards â€” a scannable card that lets a driver check themselves in at any simulator, with a permanent code that stays theirs across every card they are issued.
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
- Renamed the paid coaching choices to Pro 5Ã— and Pro 20Ã— consistently across the app, Coach, support, and backend responses.
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
- Speed coaching gives a real target ("aim about 60 mph mid-corner") plus the delta vs your last pass â€” not only "+9 mph more."
- Speeds default to mph; distances use meters to match track boards (refined further in 2.26.55).
- Removed confusing "you'll be at Turn X in about N seconds" countdowns (they were a rough distanceÃ·speed guess and often wrong once you brake).

## TrackPro V2 2.26.53 - 2026-07-08

- Fixed pre-corner coaching language: approach cues now say what to do next ("brake about 15 meters later") instead of diagnosing a brake you haven't made yet ("15 meters early on the brakes").
- While working one focus corner, pre-corner radio no longer calls secondary corners you aren't coaching.
- Clearer live position for the coach: "where am I" uses the live landmark snapshot and should not invent a different corner from chat history.
- Outlap stays quiet for unprompted coaching (tires, warmup). Proactive technique radio starts on the first flying lap after you cross start/finish; if you key the radio and ask, the coach still answers.
- Hardened pin/switch, guided-lap phrasing, and delivery so cues are less likely to fire at the wrong moment or double-talk.

## TrackPro V2 2.26.52 - 2026-07-08


- Live AI Coach focus: ask to work on a corner (e.g. "focus on Turn 4") and coaching sticks there immediately â€” no more "we can't switch" style pushback.
- Cleaner pre-corner radio: measured distances stay realistic (no absurd hundred/thousand-meter callouts), and open tips no longer spam other corners while you're focused on one.
- If a fix isn't landing, the coach escalates how it teaches the same corner (pressure, sequence, eyes) instead of only repeating the same one-liner.
- Instant post-corner feedback is more honest: one good pass is "on the mark"; "that's fixed" waits until you've held it for two clean laps.
- Live voice cost/quality tiers: Starter uses the efficient Realtime mini model; Pro and Elite use full Realtime 2.1 for the best tool-following coach.

## TrackPro V2 2.26.49 - 2026-07-08


- Proactive corner cues now include the measured figure ("you're about 15 meters late on the brakes") for the technical coach, so you get the number without asking.
- Gear coaching: ask what gear to be in and the coach compares the reference's apex gear to yours; it can always report your current gear.
- Consistent reference answers: the coach explains the reference the same way every time (a per-corner best composite from laps as quick as a stated time) instead of flip-flopping on whether it has a lap time.
- "Was that an improvement?" asked mid-lap now returns "finish the lap and I'll confirm" instead of sounding blind.
- Start Coach no longer fails silently â€” it tells you when mic/headphones need setup and points to Voice Setup.
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
- Fixed an iRacing controls/calibration freeze risk that could happen when the virtual pedal device stopped responding. TrackPro now checks that the pedal output is working, rebuilds the virtual pedal device if needed, and â€” if it still won't respond â€” leaves your physical pedals available instead of getting stuck.
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
