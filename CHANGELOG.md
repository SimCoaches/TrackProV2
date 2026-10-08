# Changelog

## TrackPro V2 2.26.230 - 2026-10-08 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.229 is included. AI Coach v0.260.

AI Coach (v0.260)
- The brain's coach runs on your PC. TrackPro downloads the brain's small coaching model (about 6 MB, cached) and, after every clean timed lap, reads the corners where the lap lost the most time to the fast drivers in your car: how much, and whether it went in the braking zone, on entry or on the exit, from your inputs and how the car responded. It runs in the background on its own thread, never on the radio's, and never touches the lap save.
- In practice, Blip calls it: "Turn 5, 3 tenths, mostly on entry. Carry more speed to the apex." Only when the measured comparison with the fast drivers and the brain's own read agree on where the time went, at most every other lap, never over the corner you are working on, a corner you muted, or one the fair test is holding back. The braking fix is to come off the brake sooner and let it roll, never "brake later". iRacing, on corners with fast-driver data for your car.
- Races and qualifying stay quiet as before: ask "where am I losing time?" and Blip answers against the fast drivers.
- Every lap's read is also logged next to what the lap measured, so the staff Brain page shows how the brain does on real laps.

Server (already live, no update needed)
- The brain's full-rate model is now 209M parameters, trained nightly on every saved lap at 60 readings a second; a small model learns from it every night and reaches PCs only when it beats the one they have.

Before acceptance:
- iRacing practice with Blip on, 6+ clean laps on a car and track with fast-driver data: within a few seconds of a lap, Blip calls a corner, its phase and the fix, at most every other lap, and never the corner of the current focus.
- The same in a race: no brain calls volunteered; "where am I losing time?" is answered.
- Settings > Diagnostics (or a bug report): coach.brainwhy reads appear for each clean lap.
- Frame rate and radio stay smooth at the moment a lap completes.
- Update from 2.26.229 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.229 - 2026-10-07 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.228 is included. AI Coach v0.259.

Wheel Studio (LEDs & Dash, still in shop testing)
- Your wheel's LEDs follow the game with one click. Wheel Studio picks the wheel that is plugged in, "Apply complete setup" turns its LEDs on, and the device bar says "LEDs off - Turn on" when they are off. TrackPro still never takes a wheel you did not turn on, and warns you if SimHub is running too.
- A USB hiccup no longer switches a wheel's LEDs off for good: TrackPro reconnects on its own. Only a wheel that another program keeps holding is turned off, and it tells you so.
- Wheels light the way their makers set them up. Each wheel's rev, side and button lights come from the vendor setups in SimHub's device files (used with SimHub's permission): which light is which, the rev colors and where they start, ABS and TC on the side lights, flags, pit limiter. 18 more wheels get their own side lights instead of a rev bar spread across them.
- Per-car rev lights: in ACC and iRacing, wheels whose maker publishes a car's shift lights show that car's own pattern.
- Lock-up lights: front wheels locking light the left side lights, rears the right. ABS still wins while it is working. Assetto Corsa now shows ABS and TC on the side lights too.
- Button lights: backlights stay on when TrackPro takes the wheel. Click buttons on the wheel photo to color them and choose when they light (always, pit limiter, pit lane, TC or ABS on, flags).
- A live "Game to wheel" line under the wheel shows the sim, updates per second, rev % and any write errors, so you can see where the data stops.
- Moza: pick your rim (CS V2.1, CS Pro, KS Pro or your own LED count); button LEDs; a note when Pit House is holding the wheel. Fanatec: TrackPro asks the base which rim is fitted. Two identical GSI wheels no longer clash.
- Wheel dash: warnings are short pop-ups that keep gear and shift lights on screen instead of taking it over; shift lights start near the shift point and flash at it, with a pit-limiter pattern; every flag (green, white, checkered, black, meatball, red); delta in ACC; a default dash on a screen that was never set up; a brightness slider; your units; a dash instead of fake zeros. New look: rounded cards, a rev arc round the gear, gradient headers.

AI Coach (Blip, v0.259)
- Blip's level is now kept on your account, so every PC shows the same Blip. Your history counts: every session where you and Blip talked on the radio, from your first one.
- A real conversation now counts as a session together, even without a lap.
- Blip remembers your last sessions together: what you worked on, what you told him and what you agreed to try next, and picks up from last time in practice when it fits. In qualifying or a race he only brings it up if you do. See and delete these under "What your coach remembers".
- He greets you like someone he knows and follows your preferences without reading his notes back to you. His memory keeps what matters about you as a person ahead of lap times, and a note about one track is only used at that track.

Setup Shop
- One-click AI setups only build from fresh garage saves, the server checks its own garage capture, and misplaced or never-loaded files retire.

Server (already live, no update needed)
- Blip memory database changes and the driver-memory-digest, ai-coach-voice and ai-coach-realtime-token functions.

Before acceptance:
- GSI GT-MAX32, iRacing and ACC: Turn on in Wheel Studio; rev lights fill with rpm and flash at the shift point; side lights show ABS and TC; a lock-up lights the matching side; all 13 buttons stay backlit; the "Game to wheel" line counts updates with 0 errors.
- GT-MAX32 screen: the dash shows on the wheel; a low-fuel or flag warning pops up and clears, gear stays visible.
- Close TrackPro and reopen: the wheel lights again without pressing anything.
- Practice with Blip on a second PC: same level; he picks up from last time.
- Update from 2.26.228 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.228 - 2026-10-07 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.227 is included. AI Coach v0.258.

AI Coach (v0.258)
- Focus calls ("let's work on Turn 5") play again for drivers without the live coach voice. Since 2.26.216 the radio refused them because the coach voice had not rendered the line yet, so they were never heard. The coach now renders the line first (up to 10 seconds) without holding up the lap, drops it if you pinned another corner, reset, pitted or started a race meanwhile, and only scores it on corners driven after you heard it.
- "Where am I losing time?" and "What should I work on?" can answer against the fast drivers in your car, from lap 1 and without a reference lap of your own: "Against the fast drivers in this car, most time at Turn 5, 4 tenths, on the exit." Clean, timed iRacing laps only; a car that has not driven that corner gets a reading only from 0.2 s and is called an estimate. Never volunteered.

Spotter
- Incidents say what happened, never the points: "We made contact with a car", "We made contact with the wall", "We lost control there", "We went off track", several takes each. A wall and a spin both score 2x in iRacing, so the spotter tells them apart from the impact the car felt (checked against 2,473 real incidents). Near the incident limit it adds "You're close to the incident limit."
- Salty and Unfiltered language levels get their own incident lines ("Damn, we traded paint." / "Holy fuck, we lost it."); Clean stays clean.
- Green flag is "Green, green, green!", and yellow, local and full-course yellow, blue, black and red each have more than one way to be called.

Setup Shop and Race Engineer
- One-click install of TrackPro AI setups, from the first driver's verified garage save.
- Race Engineer HUD: your TrackPro AI setup's garage checklist, live in the sim.
- Every setup verdict saves exactly which controls moved.

Server (already live, no update needed)
- The brain now also trains on every saved lap at 60 readings a second with 65 channels (tyre temperatures, wear, pressures, brakes, suspension); the first full-rate model is live (104M parameters).
- Market Spotter voices record the new incident and flag lines.

Before acceptance:
- Practice without the live coach voice: after a lap you hear "let's work on…" in the coach voice.
- iRacing, new car and track, lap 1: ask "where am I losing time?" and hear the fast-driver answer.
- iRacing: one wall hit, one spin, one car contact: the spotter names each correctly, with no "x" points.
- Green flag at a race start or restart: "Green, green, green!".
- Update from 2.26.227 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.227 - 2026-10-07 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.226 is included. AI Coach v0.257.

AI Coach (v0.257)
- The fair test. In practice sessions, when the coach is about to take on a new corner to work on, it sometimes waits instead: one time in ten, chosen at random, it stays quiet about that corner until the next laps through it are measured. Comparing those corners with the ones it spoke about shows how much the coach's calls really help, which the old comparison could not (the coach always picked the worst corner, and the worst corner tends to improve by itself).
- Never in races, qualifying or warmups, never the first call of a session, never a corner you asked about ("work on Turn 5" takes that corner out of the test at once), at most three times a session and at least five laps apart. Questions are answered in full as always, including about that corner.
- While a corner is in the test, the lap summary leaves out its "biggest loss" line instead of naming a smaller loss as the biggest.

Server (already live, no update needed)
- Staff Brain page: a "Fair test" card on the Coach tab (calls given vs held back, and whether the gap is bigger than chance), and the full-rate driving model card: the brain now also trains on every saved lap at the full 60 readings a second with 65 channels, including tyre temperatures, wear, pressures, brake temperatures and suspension, and each night tries a bigger model, keeping it only if it wins.

Before acceptance:
- iRacing practice with Live Coach on, 10+ laps: coaching works as in 2.26.226. Over several sessions the Brain page's "Fair test" card starts counting calls given and held back.
- In a held-back moment (rare): no call, pre-corner cue or lap-summary "biggest loss" about that corner for the next couple of laps, and asking "where am I losing time?" still names it.
- Say "work on Turn N" for any corner: the coach works on it right away.
- iRacing race session: the coach behaves exactly as in 2.26.226 (no held-back calls).
- Update from 2.26.226 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.226 - 2026-10-07 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.225 is included. AI Coach v0.256.

Laps and corner data
- Every driver's corner times now upload, for every sim. Since 2.26.177 they only uploaded for drivers who had switched corner sharing on, which almost nobody had. The coach and the brain learn from all driving, always without names. The only sharing choice left is whether other drivers can find your laps by name on the Telemetry page.
- Laps the sim never timed are now saved (marked untimed) instead of dropped, and a late iRacing lap timer no longer loses the lap. About one lap in four the coach measured was not being saved.

AI Coach (v0.256)
- Calls are graded against the same fault with no call, so the coach's learning compares like with like.
- No "keep a little brake into the turn" on paved ovals, and only at corners where the reference lap trail-brakes. That call was leaving drivers slower than saying nothing.
- Calls the nightly model finds unhelpful stop being volunteered (a pinned corner and direct questions still get them).
- Corners taken flat say so, instead of reporting the previous corner's brake and throttle points. Long braking zones are measured from their real start.
- Turn-in and throttle can be spoken against trackside references ("10 meters before the 100 board").
- First out lap sets the plan, lap 1 is the baseline, and coaching starts on lap 2.
- Guided laps are called by the lap instructor, a second voice; Blip says when it hands over.

Race Engineer and FFB
- Race Engineer suggests only controls the car really has, skips ones already at their limit, recognises the change you made, and changes one thing at a time on the radio too.
- FFB on wheel buttons: on/off and strength up/down mid-race. Once started, FFB starts by itself every session until you press STOP.
- Brake Approach overlay: an optional soft count-in and chime on the brake mark.

Settings
- "Use my laps in AI Coach comparisons" is gone: every lap trains the coach and counts in anonymous comparisons. Telemetry sharing still decides whether other drivers see your laps by name.

Server (already live, no update needed)
- Corner data lost since 2.26.177 was rebuilt from saved iRacing laps with the app's own corner code (119,000 corner passes, checked against live data first). It runs nightly for any saved lap that arrives without corner data.
- Staff Brain page (desktop Operations > Brain, and trackpro-mobile.vercel.app/brain): training, every track driven, corner maps pinned to iRacing's turn numbers, corner-data alarm, coach against silence, and whether drivers are getting faster.

Before acceptance:
- iRacing practice, 5+ laps with Blip on: after the session, corner_pass_events has rows for each lap with metrics.source empty (live), and the Brain page's Corner data line for iRacing stays green.
- Assetto Corsa practice, 5+ laps: corner rows arrive for each lap (this sim had 0% corner data in the last 7 days).
- A lap with an off or an untimed lap (pit exit, reset): it appears in Telemetry, marked untimed or invalid, instead of missing.
- Settings > Privacy: only "Share telemetry laps" shows, with the line that every lap trains the AI Coach.
- Paved oval (e.g. Charlotte): no trail-brake call.
- Update from 2.26.225 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.225 - 2026-10-06 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.224 is included. AI Coach v0.255 (unchanged).

Blip page
- "He already found time in your laps" and Corner mastery now judge each lap by the time saved with that lap. On iRacing, TrackPro versions before 2.26.186 stored the previous lap's time on every corner. A clean lap after an off or a pit stop was then left out as slow, and an off could count as a normal lap. Older sessions now show corrected numbers; laps from 2.26.186 on were already right.

Server (already live, no update needed)
- Every saved corner is linked to the lap it was driven on when it is read. On AC, ACC, rF2 and LMU, corners saved before 2.26.224 sat one lap low. On iRacing, corners saved before 2.26.186 carried the previous lap's time. No stored data was changed. The AC lap copies flagged in 2.26.224 are never linked.

Before acceptance:
- Blip page on an account with no plan whose newest outing is an iRacing session from before mid-September: "He already found time in your laps" shows corners and times, with no error.
- Corner mastery on the Blip home and on a combo page, for a combo with recent laps: grades and times show as on 2.26.224.
- Update from 2.26.224 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.224 - 2026-10-06 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.223 is included. AI Coach v0.255.

AI Coach (Blip)
- On Assetto Corsa, ACC, rFactor 2 and Le Mans Ultimate, Blip now uses your sim's lap numbers. These sims count completed laps, so Blip ran one lap behind the HUD: it said "you're on lap 3, 2 laps done" while the HUD showed lap 4. This applies to lap verdicts, "what lap am I on", lap reports, corner breakdowns and the projected pit-stop lap. iRacing and F1 were already right.
- "Compare my laps" now compares the laps you asked for. On those four sims it could read the lap before or after the one named, so the time and corners it reported came from a neighbouring lap.
- Blip downloads the brain's corner profiles (checked every 30 minutes, cached on the PC). After each lap it records, without saying anything, where the profiles say time went, so those calls can be measured before Blip ever speaks one.

Spotter
- rFactor 2 and Le Mans Ultimate now read your first lap's time. Before, the spotter never read lap 1 of a stint, and it counted every later lap one low internally.

Telemetry
- On Assetto Corsa, lap 1 (and lap 0 on races captured from the start) is no longer saved as a copy of lap 2. AC publishes the new lap time one frame before its lap counter. So the lap was stored under the previous number, then again under the right one.
- On AC, ACC, rF2 and LMU, the corner data shared from your laps now links to the right saved lap. Before, it was one lap low.

Before acceptance:
- AC practice from the pits, 3 laps: under Telemetry, stored laps 2 and 3 each have their own time and window, and there is no lap 1 copied from lap 2.
- AC with Live Coach on, a few laps. Ask "how was that lap" and "what lap am I on": the numbers match the AC HUD. Ask "compare my last lap with my best": the laps it names are in the Telemetry lap list with those times.
- iRacing, the same questions: the same numbers as on 2.26.223.
- LMU or rF2 if available: the spotter reads the lap times of laps 1, 2 and 3.
- Update from 2.26.223 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.223 - 2026-10-06 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.222 is included. AI Coach v0.254.

AI Coach (Blip)
- Blip's corner targets now come from the TrackPro Brain trained nightly on the server: more corners and more cars than the model bundled with the app, which stays as the fallback. The app checks for a new model every 30 minutes, downloads it once (under 200 KB), validates it and switches over; any failure or a server rollback keeps the bundled model. Nothing waits on it.

Onboard recording
- Triple-screen rigs now record the centre screen, the view ahead. Before, the recorder picked whichever screen the iRacing window covered most; with three equal screens that was a tie and it took a side screen, so the video showed the roof and side window instead of the road (Red Bull Ring, 2026-10-06). Single-screen setups are unchanged.

Before acceptance:
- Triple screens, onboard recording on, two laps anywhere: the lap's video under Telemetry shows the forward view through the windscreen.
- Single screen: unchanged, the video still shows the whole iRacing window.
- Coach on: within a minute of opening TrackPro the newest brain model is loaded (localStorage trackpro.brain.cornerModel.v1 shows runId 2); corner targets still work offline.
- Update from 2.26.222 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.222 - 2026-10-05 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.221 is included. AI Coach v0.253.

AI Coach (Blip)
- The reference follows the database while you drive. A quicker clean lap another driver banks during your session, practice or race, becomes the reference within about twenty seconds, and the coach says so once: "the reference is now 1:59.2 (was 1:59.9)". In a race it waits for the lap line and never interrupts a battle; never in qualifying, never with a name. Before, another driver's lap took up to ten minutes to count and the coach never mentioned the change. A failed check never throws away a good reference.

Spotter
- Spotter Market voices say their own turn numbers. Numbered turns were never built for Market voices, so the stock voice read "Turn 4" right after your chosen voice's "Careful into". Every voice now records Turn 1-51, a voice can't go live without them, and published voices back-fill once.
- Installed voices fetch every new line the server has, whatever corner naming you use, still only while the radio is quiet.

Before acceptance:
- Practice at a combo where another driver is also running (or bank a quicker lap on a second account): within about 20 s of their lap the coach says "the reference is now ..." once, and the next verdicts compare to the new lap.
- Qualifying: no reference-moved line.
- Spotter with a Market voice and corner naming set to numbers: "Careful into Turn 4" is all in your chosen voice.
- Update from 2.26.221 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.221 - 2026-10-05 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.220 is included. AI Coach v0.252.

AI Coach (Blip)
- Brake points are spoken as trackside markers wherever a verified marker is in reach of the mark: "brake right at the 100 board", "brake between the 100 and 50 boards", "brake about 20 meters past the bridge". The marker replaces the meters; "brake 30 meters later" is only said where no marker is in reach. Before, a marker was only used within 15 meters of the mark and was tacked on after the meters.
- The quick pre-corner call, the guided lap and Blip's corner answers all use the markers. The corner answer also names where you brake now against the same objects ("you braked at the 150 board, the reference brakes at the 100").
- Longer marker lines start earlier so they finish before the mark they name.
- The plain-words coach hears board names but never a meters figure.
- Markers come only from the verified set for the exact sim layout; nothing is guessed. The set is filled per track from onboard footage, starting with Red Bull Ring Grand Prix.

Before acceptance:
- Onboard recording on, 2-3 laps at Red Bull Ring Grand Prix (iRacing, cockpit view): laps are listed with video under Telemetry, so the boards can be placed from them.
- Until markers are verified for a layout, every brake cue still reads in meters exactly as in 2.26.220.
- Update from 2.26.220 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.220 - 2026-10-04 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.219 is included. AI Coach v0.251.

AI Coach (Blip)
- The reference is the fastest clean lap another driver has set for your exact car and track, one driven lap, and every driver's clean laps count. Race night 2026-10-02 at Navarra: the coach held a 2:10.1 "community reference" all evening while a clean 1:59.9 from another driver sat in the database, because the number came from a corner pool that only counted drivers who had switched on an off-by-default "share corner data" toggle. That toggle no longer gates what the coach knows; "Use my laps in AI Coach comparisons" is the only opt-out, and lap sharing by name is unchanged.
- That lap's own corners are the targets from your first flying lap; the stitched per-corner composite fills only corners it did not cover. Your own corner stays the target where you already beat it.
- As you go out the coach says what it is comparing you to: "The fastest clean lap here in this car is a 1:59.9 from another driver, and its corners are your targets from your first flying lap." If your own lap is the fastest in the database it says so.
- The "Share corner data" switch is gone from Coach settings: it no longer changed what the coach knew, so it is not offered. "Use my laps in AI Coach comparisons" (Settings → Sharing and Coach settings) is the one opt-out, and it removes your data from other drivers' references only.
- When the fastest-lap read is unavailable (offline, free plan) the coach falls back to the anonymous corner composite and says so; it never calls the composite "one driven lap by another driver".
- The coach never explains a benchmark away as a database lag or delay; when you say a faster lap exists it checks the fastest-lap tool.

Support agent
- The Support agent now knows the Spotter and Blip. "My spotter isn't talking" starts with the cause it usually is: whether TrackPro sees your sim at all (the first dot in the title bar reads No Game until you are in the car), then whether the Spotter is switched on, then where the radio is playing. On 2026-10-04 a driver asked why he could not hear the spotter, and the agent only checked his microphone.
- New checks it can run: a Spotter and Blip status read (sim connected, Spotter switch, volumes, voice, the radio output both share, and the Spotter's last decision and why), and turning the Spotter on or off with your approval.
- New starting points on the Support page: "Spotter silent" and "Blip / AI Coach".
- iRacing not detected: it no longer guesses about install drives (TrackPro reads iRacing's live feed, not its files). It asks you to sit in the car, then checks irsdkEnableMem in app.ini and whether iRacing and TrackPro are started the same way (Run as administrator).
- The Spotter is free with every account; the agent will not tell you otherwise.

Before acceptance:
- Navarra, MX-5, practice, after the coach server update: the out-lap opener names the fastest clean lap another driver set ("The fastest clean lap here in this car is a 1:59.9 from another driver...").
- Support page, iRacing closed: "Spotter silent" -> the agent runs the status check and says no sim is connected before asking about audio.
- Support page, Spotter switched off: the agent offers to turn it on; approving flips the switch on the Spotter page.
- Support page on a free account: "Blip / AI Coach" -> the agent explains Blip needs a paid plan and points to Settings > Account, without quoting a price.
- Update from 2.26.219 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.219 - 2026-10-02 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.218 is included. AI Coach v0.250.

AI Coach (Blip)
- In-car dials from the radio: "lower my traction control", "ABS up one", "bias to 54", "two clicks more front bar", "engine map 3". Blip works iRacing's F8 box for you and proves the change in the car's own telemetry, then says before and after ("traction control 1 to 0"). The first time on each car it learns the F8 row order while you are stopped in the pits or garage (one click up and one back down per row); on the move before that it says so and asks you to say "learn the in-car box" when you are stopped. Brake bias waits until you are off the brakes. If the box ever moves the wrong dial, Blip puts it back and tells you. Last night (2026-10-02) it answered "lower my traction control" with "I don't have a direct control here".
- "Read me Thomas's lap every lap" is a standing order now: every time that car completes a lap, Blip calls the time to the millisecond with the gap to your own last lap ("Thomas: 2:00.036, 0.8 quicker than your last"). Last night it said an automatic lap call wasn't supported.
- Asking about a driver now includes their live speed and position on the lap, their last and best laps and laps done, so "how fast is Michael going" has an answer instead of "I don't have his live speed".
- iRacing gaps at the start/finish line: for a few seconds every lap the gap to the leader and the car ahead read a whole lap too long (7 s read as 103.8 s last night, so "you're not catching him" was said off a wrong number). The gap now wraps correctly through the line.

Spotter
- iRacing lone qualifying: no more "Cars coming behind. Don't pull out yet." when nobody can reach you. The other cars share the session but not the track.

Voice chat
- A screech guard on both ends. A wireless headset breaking up or a feedback howl (last night: one driver's mic put a screech through everyone's headphones) is cut from the channel the moment it is detected, on the sender's PC and again on every listener's PC, for 1.5 seconds, longer if it keeps coming back. Speech, breathing and rig noise under a voice are never cut. Each cut is logged so the next one can be diagnosed.

Force feedback
- Everything in 2.26.218 (Assetto Corsa force feedback works: gain held at 5%, never 0).

Before acceptance:
- iRacing, a car with TC and ABS (GR86, GT3), stopped in the pits with TrackPro FFB/pedals as usual: say "learn the in-car box". Blip clicks through the F8 rows and says what it learned; every dial reads the same afterwards as before.
- On track: "lower my TC" → the F8 box shows TC one lower within a second and Blip says "traction control 2 to 1". "ABS to 4", "bias to 55" (off the brakes) land the same way; "bias forward" while braking is held with "Off the brakes first".
- A car with no TC (MX-5): "lower my TC" → Blip says the car has no traction control and names what it does have.
- Race: "read me <leader>'s lap every lap" → one call per lap with the gap to your own; "stop that" cancels it.
- "How fast is <name> going" → a speed in your units, with where they are on the lap.
- Race, as you cross the line behind the leader: the gap to the leader on the radio stays sensible (never a lap too long).
- Voice chat with two or more PCs: a whistle into the mic cuts for about 1.5 s on everyone's end; normal talking, laughing and breathing never cut. Gabe's headset on the next race night: if it still screeches, the log says whether it was a tone or a hiss.
- Lone qualifying: no traffic calls while alone on track.
- Update from 2.26.218 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

Not yet run on a rig: the F8 box walk on a real iRacing install (row order, the F8 toggle, whether the selection wraps on any car). The design refuses to move a dial it cannot prove and undoes a wrong one, so a failure reads as a message, never a silent wrong click.

## TrackPro V2 2.26.218 - 2026-10-02 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.217 is included. AI Coach v0.249.

Force feedback
- The Force Feedback page now drives the wheel in Assetto Corsa. TrackPro reads AC's steering force from the game's shared memory, and that channel is published after AC's own force-feedback gain. TrackPro used to turn that gain to 0 to keep AC's force feedback out of the way, which also blanked the steering force for the whole session: the page said "Force paused: car not in world" to a driver who was on track (reported 2026-10-02 from a Content Manager launch). TrackPro now holds AC's gain at 5% while TrackPro FFB is on, divides that 5% back out so the wheel gets the full force AC computed, and puts the driver's gain back when TrackPro FFB turns off, exactly as before. AC's minimum-force setting is held at 0 for the same time and restored with it.
- An install that an earlier build left at gain 0 is lifted to 5% automatically the next time TrackPro FFB is on with Assetto Corsa and Content Manager closed; until then the page says "Gain 0 — at 0 Assetto Corsa sends no steering force" with what to close, instead of a message about the car.
- The page never again judges one sim by another sim's last frame. When the sim changes, or no steering force has arrived yet, it says "no steering force from the sim yet" and the wheel is held at zero.

Before acceptance (Assetto Corsa via Content Manager, a wheel in the FFB page):
- With Assetto Corsa and Content Manager closed, press On in the FFB page: the Game force feedback card shows Assetto Corsa "Off — Held at 5% by TrackPro". Launch AC through Content Manager, drive: the page shows "Driving your wheel" and the wheel has steering force that scales with the Strength slider.
- Press Off, close AC and Content Manager: the Assetto Corsa gain in controls.ini is back to the value it had before (the card shows "On" in grey).
- An install still at gain 0 from 2.26.216/217: with TrackPro FFB on and AC running, the card says "Gain 0" and what to close; after closing AC and Content Manager for a few seconds it changes to "Off — Held at 5% by TrackPro".
- iRacing still drives the wheel as in 2.26.217, and switching from iRacing to AC (or back) in one TrackPro run shows no stale message from the other sim.
- Update from 2.26.217 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

Not yet run on a rig: the feel with Content Manager's FFB post-processing (LUT or gamma) enabled. If the force feels wrong with post-processing on, turn it off in Content Manager for this build and report it.

## TrackPro V2 2.26.217 - 2026-10-02 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.216 is included. AI Coach v0.249.

Pedals
- Calibration now finds the throttle on another port. If a throttle's sensor lead has been moved to one of the other leads inside the back of the pedal, the "press the throttle" step sees the movement on that port and fixes the mapping automatically, exactly as it already did for the brake and clutch. The same Undo is there if it guessed wrong.
- Nothing changes for pedals that are wired normally: a throttle that moves on its own port is confirmed as before, and a pedal only moves to another port when that port alone moves clearly while the throttle's own port stays still.

Before acceptance:
- A pedal set wired normally: run calibration; every pedal is confirmed on its own port and drives normally afterwards.
- The throttle with its sensor on another lead: run calibration, press the throttle at its step; the page says it found the throttle on that port and fixed it; finish calibration; the throttle drives the throttle axis in the game, and the brake and clutch are unaffected.
- Update from 2.26.216 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.216 - 2026-10-02 (stable)

Promoted from the signed beta without rebuilding the installer, after a drive on the owner's rig. This is the stable release: it carries every change since 2.26.181 (the entries below). The Lebois SRT80 has not been run on a rig and stays a beta-channel option. AI Coach v0.249.

Motion
- Stop releases the controller, and now says so. Pressing Stop has always parked the rig and then closed the controller's port, but the Motion page kept showing "Rig connected" and a Disconnect button, so it looked as if TrackPro was still holding the controller. After Stop the page now shows the rig as not connected, with: "Motion stopped. The controller is released, so other software can use it. Press Enable to use it here again." SimHub and other software can open the controller as soon as that appears (a few seconds after Stop, once the rig has parked).
- Correction to the 2.26.215 notes, which said TrackPro keeps the port until Disconnect: it does not. Stop and Disconnect both release it. E-STOP keeps the connection, because the rig is being held and motion resumes from there.
- If an SRT80 cannot be lowered in time on Stop, TrackPro says the rig is still held up instead of saying the controller is free.

Checks used for acceptance:
- Thanos rig: Enable, drive, press Stop. The rig parks, then the Motion page shows "Rig not connected" and the released message. SimHub can open the controller without closing TrackPro. Press Enable in TrackPro (with SimHub's connection closed): motion works with the same settings.
- Press E-STOP while running: the Motion page still shows the rig connected; Enable resumes.
- Beta channel off: Motion setup and Settings list no Lebois SRT80. Beta channel on: both list it.
- Thanos rig: enable motion, close TrackPro, open it again. Motion is not armed and SimHub can open the controller's port.
- Practice, three or more flying laps so the coach picks a corner: the short cue before it, "Brake now." early enough to act on, the other calls through the corner, the short verdict just past the exit.
- Update from 2.26.215 (and from stable 2.26.181) with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.215 - 2026-10-02 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.214 is included. AI Coach v0.249.

Motion
- The Lebois SRT80 is offered as a motion kit and controller on the beta channel only. Its driver has not run on a real rig yet, so an install that is not on the beta channel does not show it. A rig that is already set up on the SRT80 keeps its setup.
- TrackPro no longer takes a Thanos or SRT80 controller when it starts. Before, if TrackPro was closed with motion still enabled, the next launch re-armed motion and opened the controller's port, which locked SimHub and other software out of it. Now every motion setting still comes back at launch, and the controller's port is opened only when you press Enable or Connect (or run a test). No motion controller re-arms on its own at launch: press Enable to start motion.
- To hand the controller to SimHub in the middle of a session, press Stop (or Disconnect) on the Motion page: both park the rig and release the port.

This build is the candidate for the next stable release: the same installer is promoted if it passes.

Before acceptance:
- Beta channel off: Motion setup lists Thanos4U and MEGA+ kits and no Lebois SRT80; Settings, Hardware lists ESP32, Thanos 4U and Thanos AMC and no Lebois SRT80. Beta channel on: both list it.
- Practice, three or more flying laps so the coach picks a corner: the short cue before it, "Brake now." early enough to act on, the other calls through the corner, the short verdict just past the exit. Nothing talks over anything else.
- Suggestions per lap on 1, 2 and 3: she coaches that many corners in a lap when that many have a measured fault.
- Motion on the rig you normally drive: connect, Start, Stop and E-STOP behave as in 2.26.213.
- Thanos rig: enable motion, close TrackPro, open it again. Motion is not armed and SimHub can open the controller's port; press Enable and motion works with the same settings as before.
- Update from 2.26.214 (and from stable 2.26.181) with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.214 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.213 is included. AI Coach v0.249.

AI Coach (practice)
- She calls the corner you are working on, at the spot, every lap: "Brake now." at the reference brake point, "Turn in.", "Keep turning." (only while your steering has stopped well short of the reference), "Unwind.", "Accelerate.". A driver who brakes too early hears "Wait for it." first. The reference is your reference lap for that car and track, or your best pass this session. If you brake before she calls it, she says nothing there and tells you after the corner.
- Practice lines are short and instant. Before the corner: "Turn 5 — brake 35 meters earlier." After it: "Turn 5 — good." / "Turn 5 — better." / "Turn 5 — not yet. Brake earlier." These play from the coach's saved voice clips, so they start at once instead of one to three seconds late. The longer spoken explanation is no longer volunteered; ask her and she explains.
- Suggestions per lap is a real count. On 1 she coaches the corner she is working on with you; on 2 and 3 she adds the next-biggest measured losses at other corners. A lap with fewer measured faults gets fewer; nothing is made up to fill the number. A corner you pin stays the only corner.
- The lap note no longer names a different "biggest loss" corner every lap while she is working one corner with you.
- She never talks over an answer to you, and "less corner coaching" silences the live calls too. Qualifying and races are unchanged: quiet in qualifying, race engineer in the race.
- Race pace calls say "1.2 seconds a lap" instead of "12 tenths a lap".
- English only for now: on another coach language the cues keep the live voice.

Motion: Lebois SRT80
- Control boxes on Lebois firmware 2.1 are supported (Competition Control Box V1 and V2, four lift actuators). Firmware 1.8 and 1.9 work as before. Lebois changed the box's protocol in firmware 2.0 (June 2026) and Motion Center V1.1 installs 2.1, so an updated box could not connect to TrackPro until now.
- Firmware 2.0 is refused with a message to update to 2.1: it switches the servos off whenever the port closes, which would drop a held rig every time TrackPro closes.
- New safety gate, on every firmware: if the box's servos went off while TrackPro's record has the rig raised (SimHub or Motion Center used the box, the box's own E-stop, a fault), TrackPro will not move it. The box only counts position while its servos are on, so its count no longer matches the rig. TrackPro asks for the box's USB to be unplugged and plugged back in with TrackPro open, and connects after that.
- While a rig is recorded as held on a control box, TrackPro does not probe that port and will not connect another controller type to it.
- Nothing here has run on a real SRT80 rig yet. The first-run checklist in docs/motion-srt80.md must be done with nobody in the rig.

Before acceptance:
- Practice, three or more flying laps so she picks a corner: on the next approach you hear the short cue, then "Brake now." early enough to act on, the other calls through the corner, and the short verdict just past the exit. Nothing talks over anything else.
- Set Suggestions per lap to 1, 2 and 3 in turn: she coaches that many corners in a lap when that many have a measured fault.
- Key up and ask a question near the corner she is working on: her answer is never cut off by a call.
- SRT80 on firmware 2.1 (nobody in the rig): connect, Start (smooth rise), Stop (lowers, drivers go quiet), E-STOP while running (freezes and stays held for a full minute), quit TrackPro while running (stays held for a full minute), relaunch and Start (no jump).
- SRT80: with the rig held by an E-STOP, quit TrackPro, unplug and replug the box, relaunch: TrackPro refuses with the replug message; replug the box with TrackPro open: it connects.
- Update from 2.26.213 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.213 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.212 is included. AI Coach v0.248.

Motion
- The rig's physical E-stop reaches TrackPro. The Sim Coaches Control Center display (the touchscreen E-stop display) senses the Motion Kit and Simucube E-stops and now reports both to the PC over its Bluetooth gamepad link. TrackPro reads it: the moment the Motion Kit E-stop is pressed, motion goes to E-STOP and latches, the corner LEDs flash red, the Motion page shows a red "E-stop pressed on the rig" banner, and Enable is refused until the button is released. Releasing the button never restarts motion by itself: press Enable, as with the on-screen E-STOP.
- The Motion page shows whether an E-stop display is reporting ("Rig E-stop: ready") or not paired.
- This needs the display's updated firmware (SimCoaches/estop, "Report both E-Stop states to the PC"), flashed to the display, and the display re-paired with the PC afterwards so Windows reads its new report layout. Until then TrackPro shows "Rig E-stop: not reported".

Why this way: the Thanos4U controller never reports its E-stop over USB (its manual has no status output) and keeps accepting position data while stopped, and the SRT80 control box only shows its servo enable, so neither controller can tell TrackPro anything. The display is wired to the button and already talks to the PC.

Before acceptance:
- Flash the display firmware, remove and re-add the "Sim Coaches Control Center" Bluetooth pairing, open TrackPro: the Motion page says "Rig E-stop: ready".
- With motion running, press the rig's E-stop: the rig stops, the LEDs flash red, the banner appears, Enable is refused with "Release it, then press Enable".
- Release the button: the banner clears, nothing moves; press Enable: motion resumes normally.
- Unplug or power off the display: the line changes to "not reported" within 10 s; nothing moves.
- Update from 2.26.212 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.212 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.211 is included. AI Coach v0.248.

Corner LEDs: Race mode
A new mode under Motion > Corner LEDs drives the four corner strips like a race LED profile. The layers run top to bottom and the first cue that is on wins each corner, so flags beat the pit lane, which beats cars alongside, which beats the car's own cues.
- Flags (all four corners): red (blink), disqualified (fast red/black), black (red/black), meatball (orange chase), checkered (white chase), start lights ready/set/go (red, amber, green), white, one lap to green (green pulse), full-course caution (yellow blink), local yellow (solid), debris (slow yellow chase), furled yellow (pulse), blue (blink), green. Five to go, ten to go and halfway pulse white on the fronts.
- Pit lane: over the pit speed limit blinks red everywhere; the limiter runs a blue chase; the pit lane itself shows dim blue.
- Cars alongside: car left or right pulses amber on that side; two cars on a side pulse faster; cars on both sides pulse red everywhere.
- The car: reverse lights the rears white; ABS working blinks the rears white/red; TC working blinks them amber; low fuel (under 10%) pulses the rear-left amber; shift point blinks the fronts red; DRS open shows green on the fronts, DRS available pulses green on the rears; an RPM bar fills the fronts outward from the centre line between the car's own shift-light points; brake (red) and throttle (green) by pedal pressure on the rears.
- A green, white, start-go or halfway cue stays lit 3 seconds after the sim drops it.
- Test: every layer has a Test button that lights it on the real strips for 3 seconds, to judge the colours by eye.
- Out of a session the strips show the dim static colour. E-stop still flashes red in every mode.
- The profile is saved with the LED settings and can be edited by hand (%APPDATA%\TrackPro\motion_leds.json, "profile"); the built-in one is used until you do.

Diagnostics
- The "Telemetry source: Native 360 Hz" tile showed red on healthy rigs. The motion loop takes each 60 Hz batch the moment it lands and skips what is left of the old one on purpose, which keeps latency low, but the tile failed on any skipped sub-sample ever. It now judges a skip rate (normal up to 36 a second, fail above 120) and says what it expects.

Before acceptance:
- Motion > Corner LEDs > Race, in an iRacing race: the start lights, a yellow, a full-course caution, a blue, the white and the checkered each show on all four corners in their colour; a car alongside pulses amber on that side only; the pit limiter runs its blue chase and going over the pit limit blinks red; braking lights the rears red and throttle green; the rev bar fills the fronts from the centre line outward and blinks red past the shift point.
- Press Test on each layer and check its colour on the strips.
- Leave the session: the strips drop to the dim static colour.
- Update from 2.26.211 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.211 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.210 is included. AI Coach v0.248.

Overlays
- Overlays no longer get cut off. With Windows display scaling above 100% every overlay window came out too small for its content (80% of it at 125%, 67% at 150%), so text was clipped on the right and bottom whatever the size or position. Windows now size to their content at any display scale, and re-fit when dragged to a monitor with different scaling.
- Size is a slider from 50% to 200% instead of three sizes (your Small/Medium/Large become 75/100/150%).
- Drag any overlay anywhere with Alt+O, right up to the screen edge. Positions are kept per monitor, so an overlay on a second screen comes back there. The position presets stay as shortcuts.
- FFB overlay: the power button and the - / + strength buttons work. Overlays are click-through while locked, so every click on them went to the sim; the FFB overlay now takes clicks in its own small window without ever taking focus from the sim. Its strength range matches FFB Lab (6-60 Nm).

Haptics
- Pedal (Simagic Reactor) and shaker frequency sliders: Lo and Hi move on their own, can meet for a single frequency (one tone for ABS, for example), and never get stuck at an end. Before, moving one moved the other and a slider could lock solid. A bad frequency value can no longer stop the pedal haptics.

AI Coach v0.248
- Lap comparisons describe positions the way a driver thinks: from the corner's apex and against what you do now ("the reference is at full throttle 20 m earlier than you"), never as a distance into the lap like "5889m". Small brake gaps (under 10 m) are no longer offered as advice, and a mixed-up comparison that could tell you the reference brakes later when it brakes earlier is fixed.

Motion
- Corner LEDs: when an LED board doesn't answer, the message now shows exactly what the board sent back, to pin down boards that still won't connect.

Before acceptance:
- Overlays on a 125% or 150% display: Session Focus and Race Engineer show fully at 50%, 100% and 200%. Drag one with Alt+O, restart TrackPro: it comes back in the same spot, on the same monitor.
- FFB overlay in iRacing: - and + change the wheel's weight, power stops and starts it, and clicking it doesn't take control away from iRacing.
- Haptics: set ABS Lo and Hi to the same frequency; ABS fires at that one tone. Drag sliders to both ends; nothing sticks.
- Telemetry page lap comparison: no lap-distance positions; advice reads from the apex and against your own lap.
- Corner LEDs: if it still doesn't connect, send the message (it now includes what the board replied).
- Update from 2.26.210 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.210 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.209 is included. AI Coach v0.247.

Motion
- Chassis stiffness: four actuators can twist the frame diagonally, which no car chassis does. TrackPro now removes that twist, so every movement reaches the seat as heave, pitch and roll, like a car. A kerb under one wheel still hits hardest at that corner (three quarters of it), and the rest of the hit comes through as the body moving. New slider next to the corner mixer (Advanced), 100% by default.
- The suspension travel limit added in 2.26.208 now holds all four corners together, so it can no longer twist the frame.
- Motion monitor (new card on the Motion page): live, what each corner is sent in mm, split into cueing (braking, cornering, bumps), elevation, suspension and haptics, plus heave, pitch, roll and warp (twist). Each lap the log gets the RMS of each, including warp.
- Corner LEDs work with Pro Micro, Leonardo and Micro boards (ATmega32u4), including stock SimHub firmware: TrackPro keeps the board's DTR line up through the baud change it was dropping.

Before acceptance:
- Motion, Omega: kerbs on one wheel and on both sides. The rig moves as one body (no diagonal twist), the kerb side still reads, and the Motion monitor shows warp near 0 mm.
- Corner LEDs with a Pro Micro on stock SimHub firmware: connects, all four modes, E-stop flashes red.
- Motion monitor: numbers move with the car; the log line appears each lap.
- Update from 2.26.209 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.209 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.208 is included. AI Coach v0.247.

Motion
- Banking wins: on a banked turn the held cornering lean used to pull the rig the other way and cancel most of the bank. It now gives way by how steep the bank is, so the rig leans into the banking and holds it. Daytona at 100% overall strength: about 41 mm per side into the banking (it was about 16). The quick push to the outside at turn-in stays. Off-camber corners keep both, so they feel like they throw you out.
- Crests and compressions: over a crest the seat drops as the car goes light; at the bottom of a dip or a compression (Eau Rouge) it lifts as the car goes heavy. These ride on the elevation travel, not the bump travel.
- Tracks are mapped and anticipated: TrackPro records each track's hills, banking and height along the lap as you drive, and keeps them. After one clean lap it reads the track a moment ahead, so crests, banks and hills arrive on time instead of after the telemetry and actuator delay.
- Track feel (new card on the Motion page): the lap's climbs and drops, where the banking is, where you are on it, the steepest hill and the biggest bank.
- Ride along: replay your last clean lap on the rig without the game, looping, to judge and tune hills, banking and crests from the seat. Motion must be on; Stop, E-stop, turning motion off or driving again ends it, and the rig parks.
- Banking check: on steep banking TrackPro confirms the sim reports the bank the right way round, and corrects it for the session if not.

Before acceptance:
- Motion, Omega: Daytona. The rig leans clearly into the banking through each turn, inside down. If it leans to the outside, check the Track feel card (it should say it corrected the banking) and send logs.
- A hilly road course (Spa, Laguna Seca): first lap maps it (the card shows progress); from the second lap crests drop the seat and compressions lift it, on time. Eau Rouge and the Corkscrew.
- Ride along: drive one clean lap, stop in the pits or exit, press Ride along with motion on. Try Stop, E-stop, and driving again: each ends it and the rig parks.
- Kerbs, braking and cornering still read clearly on flat road courses.
- Update from 2.26.208 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.208 - 2026-10-01 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.207 is included. AI Coach v0.247.

Motion haptics (actuators)
- Kerb rumble hits hard on the side that's on the kerb. iRacing's kerb pitch (often 40-120 Hz at speed) was played on the actuators at up to 45 Hz, where their top speed allowed only 2-4 mm of movement and a loaded rig barely follows. The actuators now play each kerb as 10-18 Hz bumps (still faster at higher speed) at 85% of the haptics travel, under the full-strength thunk: more than 6 mm peak to peak on the struck side, nothing on the other side. The shakers keep the real kerb pitch.
- Haptics travel goes up to 5 mm. The rest of the stroke belongs to elevation and suspension.

Motion
- Travel split: every movement is elevation, suspension or haptics, and each has its own share of the stroke. Advanced > Travel:
  - Elevation (the track's shape: banking, climbing and dropping down hills, crests): by default all the stroke the safety zone leaves after suspension (85 mm on a 150 mm Omega).
  - Suspension (the car's own movement: braking, throttle, cornering lean, kerbs launching the car, bumps): 50 mm.
  - Haptics: set under Actuator haptics, up to 5 mm.
  Overall strength scales elevation and suspension together.
- Banking and hills are calibrated per track. TrackPro learns each track's biggest sustained bank and hill as you drive and sizes that track to the elevation travel, so Daytona's banking and a big climb both use the stroke, and each track's slopes keep their true proportions. The first lap on a new track learns as it goes; the track is remembered after that.
- Banking no longer cancels out: before, the track's slope, cornering lean and braking shared one angle limit, so on a banked turn the cornering lean cancelled the bank and the rig sat nearly level.
- Track elevation (Advanced) now sets how far each track's biggest hill or bank reaches into the elevation travel: 1.5 (Omega) uses all of it.
- VR compensation includes the elevation movement.

Before acceptance:
- Motion, Omega: Daytona (or any banked oval). The rig leans clearly into the banking and holds it through the turn.
- Motion: a hilly road course (Spa, Laguna Seca, Road America). You feel the climbs and the drops; the first lap learns, the second lap is the full size.
- Motion: braking, throttle and cornering still read clearly with suspension at 50 mm. Try 40-70 mm under Advanced > Travel.
- Kerbs on both sides: the kerb side's actuators rumble hard, the other side stays still. No clunks at 5 mm.
- Update from 2.26.207 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.207 - 2026-09-30 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.206 is included. AI Coach v0.247.

Motion haptics (actuators)
- Kerbs thunk: the moment a tyre touches a kerb, that corner kicks up in one short, hard hit, and the same-side corner follows at half, so you feel which side and whether it was the front or rear tyre. One thunk per kerb; the rumble follows.
- Kerb rumble stays on the tyres actually on the kerb (iRacing reports it per tyre) instead of buzzing all four corners.
- Full strength: actuator haptics now follow their own Master and Travel budget only. Since early September they were also scaled by overall motion strength, so Omega Full delivered 65% and Omega Comfort 45% of what the haptics settings asked for. Overall strength at 0 still silences them.
- Omega kerb gain 1.0 (was 0.75). Suspension impact stays at 1.0.

Motion
- Elevation first: hills, crests and banking get the travel; suspension and bump heave give it up. Omega factory tune: Track elevation 1.5 (new slider in Advanced), bump release 0.4 Hz so crests and dips are held, Bumps & kerbs 1.0 (was 1.5), corner mixer suspension 0.10 (was 0.25). Saved Omega factory profiles upgrade on their own; a profile you changed keeps your values (Restore factory settings applies the new ones).
- Corner LEDs: TrackPro drives the LED strip on the rig's corners (a SimHub Arduino), so SimHub isn't needed for them. Motion setup > Corner LEDs: pick the Arduino's port, then press Show to map each part of the strip to its corner. Motion page > Corner LEDs: Status, Movement (each corner follows its actuator), Game (rev lights and flags) or Static, plus brightness and colour. E-stop always flashes them red. Close SimHub, or turn off its Arduino connection, first: only one program can use the port.
- The response test times braking and cornering cues with the profile's cue response, the way they arrive while driving.

Haptics (bass shakers)
- Kerbs stand out again: while the kerb rumble plays, engine vibration eases to half and comes back slowly after the kerb. Road texture is unchanged. Since 2.26.204 only the kerb's first strike ducked the engine, so the rest of the kerb played under a constant engine buzz.

AI Coach v0.247
- Blip works without a microphone: he still calls corners and laps on the radio, and picks up your mic the moment you plug it in.

Before acceptance:
- Motion, Omega on the rig: kerbs on both sides at Laguna Seca or Spa. Each kerb gives one clear thunk on the right side, front then rear, then rumble. No clunks at 4.5 mm.
- Motion: a hilly track. Crests, dips and banking read clearly; suspension and bumps no longer fill the stroke. Try Track elevation 1.0 to 2.0.
- Corner LEDs: with SimHub closed, pick the port, map the four parts with Show, try each mode, press E-stop once.
- Shakers: kerbs stand clearly above the engine, and the engine comes back smoothly after each kerb.
- Blip: start with the headset mic unplugged (or blocked in Windows), then plug it in mid-session.
- Update from 2.26.206 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.206 - 2026-09-30 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.205 is included. AI Coach v0.246.

Phone control
- Motion tests started from the paired phone run at 25% speed. The axis test covers the same travel at a quarter of the frequency (8 s instead of 2 s), the corner actuator test ramps over 8 s instead of 2 s, and the full travel check moves at a quarter of its normal top speed. The PC enforces this: a phone cannot ask for a faster test.
- The full travel check can be started from the phone. The PC sends the complete motion configuration first, exactly like the Motion page, never leaves motion enabled, and runs only from Stopped (never after an E-STOP).
- If the phone disconnects within 30 s of starting a test or enabling motion, the PC stops motion.
- The phone asks the PC what it supports and keeps motion tests locked on older TrackPro versions that cannot slow them down.
- Desktop test buttons are unchanged.

## TrackPro V2 2.26.205 - 2026-09-30 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.204 is included. AI Coach v0.246.

Motion
- Lower latency on every profile. Measured stage by stage (docs/motion-latency-ledger-2026-09-30.md): on Omega Comfort the seat starts moving 20 ms after the car's G changes on a brake stab (was 69 ms), 21 ms on throttle (was 100) and 32 ms on turn-in (was 103), and reaches half the cue 93 / 33 / 40 ms after the car (was 281 / 217 / 239). Jitter on noisy telemetry is no worse.
  - The body cue takes each iRacing telemetry batch the moment it lands instead of 13.9 ms later.
  - The G smoothing opens up during a real brake stab or turn-in and stays calm on a straight.
  - The planner answers real cues fast and keeps small moves smooth.
  - Omega Comfort and Omega Full: planner limits sized to the Omega actuator (250 mm/s, 5000 mm/s², 400 000 mm/s³) and driver-input anticipation on (80 ms: steering, brake and throttle start the cue before the car's G does, once a few laps have taught it the car). Saved factory profiles upgrade on their own; a driver's own changes are kept.
  - Drivers' own tunes and non-Omega rigs get the engine fixes and keep their own planner limits.
  - Returning to center when telemetry stops or motion parks keeps its gentle limits.
  - Engineering panel: new Cue response setting; the jerk limit goes up to 500 000 mm/s³.
- Lebois SRT80 control box support (firmware 1.8+): setup kit and channel test. Rises gently after Enable, lowers on stop without blocking E-STOP, freezes in place on E-STOP.
- Phone control: the paired phone can change every motion and pedal-haptics setting and enable motion with the same safeguards as the Motion page.
- Flight: MSFS motion no longer parks on the G FORCE check; why motion stopped stays on screen during a flight.

Handbrake
- In-app firmware updater for the Arduino handbrake, with P1 Pro auto-detect and a factory flasher.
- The handbrake firmware uses its own USB ID and is hidden from games together with the pedals.

Getting started
- New PCs drive first and sign up after: laps driven as a guest are saved, and the keep-your-laps ask comes after the session. The free trial ask shows more often.
- Signup is Blip: live Blip and the logo replace the old coach art, and the setup step sets up Blip.
- A second PC keeps your recording choice, headset and wheel talk button. Signing up with an email that already has an account signs you in.
- Finished accounts are no longer sent back through setup on another PC.

AI Coach v0.246
- AI Coach allowances doubled on every plan. Free trial minutes no longer use up a new paid plan's coach time.
- Out of talk time, the coach always says so: the line waits for a busy radio, plays to its end (no 15 s cut), no longer goes silent late in a long session, comes in every coach language, and after a plan ends comes from the shared clip library.
- Talk-time heads-ups wait for a busy radio instead of being lost, and say the minutes left when they finally play.
- Starting the coach while offline shows the real network error. A capped driver hears the upgrade offer for their actual plan (Pro 20x gets none). A plan that lapses mid-session says the plan has ended and the status reads Paid Plan Required.
- Accented iRacing track and driver names (Nürburgring, Autódromo, León) are spoken and shown correctly, and each track keeps its history.
- Coach speed: guided action words ("Brake now.") and queued coach lines start on time even when the PC is busy.
- Guided lap no longer skips corner cues when a clean lap lands before the line.
- Coach and Spotter clips no longer pile up in memory over a long session: each player keeps at most 3 minutes of decoded speech; traffic and hazard calls stay preloaded.

Haptics
- No phantom shift clunk after E-Stop, a skipped frame, an effect switched back on, or haptics resuming.

Membership
- Complimentary memberships expire on time.

Before acceptance:
- Motion, Omega Comfort on the rig: the five-part feel test (quiet baseline, pure roll on a slalom, pure pitch on the pedals, kerb heave mid-corner, grass chatter). Listen for clunks on hard brake stabs. Run Motion setup > Response test and keep the saved file.
- SRT80 on a real rig (not yet run on hardware).
- Handbrake: update the firmware in the app; the handbrake still works in iRacing afterwards and isn't seen twice.
- New PC: drive as a guest, then sign up; the guest laps are kept.
- Coach: offline Start; a Pro 20x driver at the cap; a plan expiring mid-session; a long session with the Spotter off run to the cap; a non-English coach at the cap; an accented iRacing track; a 1 h+ session with memory flat and traffic calls instant.
- Haptics: no clunk after E-Stop and resume.
- Update from 2.26.204 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.204 - 2026-09-29 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.203 is included. AI Coach v0.245 (unchanged). Force Feedback is still staff-only and drives a real wheel: hands off the rim when you press Start, and start at a low Force limit.

Force Feedback page
- Rebuilt around what a driver sets: wheelbase, rotation, Force limit, Steering weight and a Feel. Steering weight now reads Lighter to Heavier.
- Setup check replaces manual calibration and the test pulses. Five rows turn green on their own as you drive: wheelbase found, the game's own force feedback off, rotation matching the game, force direction, and clipping. The force-direction row is new: TrackPro proves in grip corners that the wheel is pulled back to centre, and a backwards wheel gets a one-tap Flip. Rotation and clipping also get one-tap fixes.
- Balanced GT is the default feel for a fresh install (it was Pure physics). Saved settings are kept.
- Advanced holds only driver settings: Detail, Minimum force, Invert, and a live force bar while driving.
- The page says Connecting, not "not responding", while the engine starts, and keeps looking for a wheelbase that is plugged in later.
- A plain dial replaces the drawn wheel when TrackPro cannot identify your rim.

Force feedback effects
- Effects grey out, with the reason, in games that cannot drive them. The page follows the live game, or the game you pick. iRacing: no front lockup or traction control (it publishes no wheel speeds or TC activity). rFactor 2 and Le Mans Ultimate: no ABS or TC. F1: no suspension bumps. BeamNG: no slip, bumps, limiter or lockup. Assetto Corsa and ACC drive all eight.
- Newly working: front lockup in rFactor 2, Le Mans Ultimate and F1, and traction control in F1 (F1 23 and later). BeamNG's rev limiter no longer fires against a guessed redline. Le Mans Ultimate was never greyed before.
- Car first: effects are sized against the car's own steering force, so they stay in proportion to it at any Steering weight and on any wheelbase, with a hard ceiling each.
- Shift: a small knock through the rim on each gear change that cannot pull the wheel either way (it could reach a third of full force before).
- ABS: the steering weight pumps as front grip comes and goes, as in a real car. It only ever takes force away.
- Each effect has its own rhythm: slip is a pulsing judder that slows as the slide grows, TC a fast stutter, lockup a gritty scrub, limiter a coarse cut-and-catch under power, engine a faint hum that steps back when anything else speaks.
- Fixed: effects squashed against the force limit in loaded corners went one-sided and lightened the steering; one braking zone fired ABS, lockup and slip together; body roll on turn-in pushed the wheel as a "bump"; H-pattern shifts through neutral never knocked.

Haptics (bass shakers)
- Outputs follow amplifiers Windows renumbers, say which program holds an output (SimHub, Voicemeeter), retry every 2 seconds, and recover streams that stop.
- Dedicated mode remembers the period each output held; dropouts are counted and named by cause.
- Feel: calibrated loudness, no effects during garage animations, kerbs by strike only, shift dynamics; F1 ABS read from the wheels; iRacing straight-line lockup; slip and lockup calibrated at the kit preset volumes; the Dayton kits' 60 Hz engine ceiling shown on the page.

Community and Setup Shop
- Community has a support channel with a handoff to AI support, and unread counts on text channels.
- Setup Shop: compact header, live session card, and a searchable AI setup list that stays in view.

Before acceptance:
- FFB in iRacing (sim FFB off): all five Setup check rows go green within a few laps; tick Invert and the check flags it and Flip fixes it; a heavy car shows the clipping fix.
- FFB shifts at full Force limit on a direct-drive base: a small knock, never a yank. Sequential and H-pattern.
- FFB braking: ABS makes the steering weight pump; a lockup (AC or ACC) scrubs; no triple buzz in one stop.
- FFB each effect's Test, eyes closed: every one recognisable.
- FFB in Assetto Corsa: check whether kerbs feel doubled (AC's own kerb and road enhancement may already be in the force TrackPro reads).
- Haptics: pick an output, restart TrackPro, the same output plays; unplug and replug the amp, it recovers within seconds.
- Update from 2.26.203 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.203 - 2026-09-29 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.202 is included. AI Coach v0.245. Custom motion games are new; test them on an empty rig at low master gain first.

VR motion compensation
- TrackPro no longer touches VR motion-compensation data unless TrackPro motion is moving your rig. With SimHub or FlyPT driving the platform, OpenXR Motion Compensation no longer jumps. Before, TrackPro wrote a level rig position into the same shared memory even with its motion off.
- With TrackPro motion on, compensation works as before.

AI Coach v0.245
- Corner calls use iRacing's official turn numbers only. Numbers come from iRacing's own track maps, placed on the line drivers actually take. A layout whose map can't be verified stays silent rather than guess a number.
- Blip's ElevenLabs voices (the shared voice catalog and every Spotter Market voice) run on ElevenLabs' newest speech model, Eleven v4 Turbo, and fall back to the previous model automatically. The server side is already live for every version; this build keeps Blip's saved lines matched to the model in use and remembers it across restarts.

Spotter
- Corner calls use iRacing's official turn numbers, the same as Blip.
- Custom voices, already live on the server for every version: the three samples are three genuinely different takes on your description (voice range, texture and attitude), made with ElevenLabs' newer voice designer. Voices no longer have a radio filter baked in (TrackPro adds the radio sound). Accents you ask for stay strong, and you can name your voice whatever you like.
- In this build, the voice studio pre-selects the pace and energy that suit your voice's personality. You can still change them.

Custom motion games
- A game built to TrackPro's motion integration guide (Generic Motion Telemetry v1) can now drive the motion platform. It sends UDP to port 5101 on the same PC.
- TrackPro recognizes the game by its packets, hands the rig to iRacing or a flight sim the moment one starts, and parks the rig when the game pauses or stops. The game never reaches lap capture, Blip or the Spotter.
- The Motion page's engineering panel adds Custom motion games settings: joystick cue strength, joystick ramp and rotation onset.

Before acceptance:
- SimHub (or FlyPT) motion with OpenXR Motion Compensation, TrackPro running with its motion off: the headset view stays still with no jump every second.
- TrackPro motion with OpenXR Motion Compensation: compensation still follows the rig while TrackPro motion is enabled.
- Custom motion game on an empty rig at low master gain, using the bench sender (scripts/send-trackpro-motion.py circle, thrust, joystick): the rig leans the right way, the joystick moves it only while its cue is on, and it parks when the sender stops.
- Blip in an ElevenLabs voice for a session: every reply in the chosen voice, no gaps.
- Spotter and Blip at Road Atlanta and VIR: corner numbers match iRacing's.
- Voice studio: design "grumpy old spotter"; the three samples are clearly different voices.
- Update from 2.26.202 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.202 - 2026-09-27 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.201 is included. AI Coach is unchanged (v0.244). FFB Lab changes are new; keep FFB testing supervised.

League Night
- Your result is kept even when the whole field finishes at once: a save that fails is retried until it lands, and it waits across a TrackPro restart.
- The result is taken once the race goes green. A session that ends on the grid, in the warm-up or on the parade lap no longer records your grid slot as your finish.
- Already live on the server for every version: scoring no longer runs inside your result save, a wrong PC clock no longer drops your result, your real finish replaces an early guess, and a driver whose result never arrived is placed from the race's classified order by name. Week 6 (Snetterton) is corrected: three missing drivers are scored and one misplaced finish is fixed.

Profile pictures
- Google profile pictures load again on the Race Pass leaderboard, Social, friends and profiles. A picture that can't load shows the driver's initials instead of a broken image.

FFB Lab
- When the wheel's force stops mid-session, TrackPro notices within about a tenth of a second (was half a second) and brings it back with a 0.4 s ramp, well under a second in all.
- Each force loss is logged with the USB devices that changed just before it.

Before acceptance:
- League Night: finish a hosted iRacing race on this build; your result is on the League page within a minute. Pull the network cable at the finish and reconnect: the result still arrives.
- Race Pass leaderboard and Social: drivers with Google pictures show their photo; nobody shows a broken image.
- FFB Lab on a supervised rig: unplug and replug the wheelbase USB mid-session; force returns within a second, and the log names the device.
- Update from 2.26.201 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.201 - 2026-09-27 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.200 is included. FFB Lab changes are new; keep FFB testing supervised.

AI Coach v0.244 - fixes from the field
- The Blip page no longer flashes the "Meet Blip" sign-up page for drivers who already have Blip when switching pages. It waits a moment for your account to load.
- Circuito de Navarra (Speed Circuit): Blip names the corners from the real start/finish line. It had been calling Turns 2 and 3 "Turn 5" and "Turn 6".
- Blip in a Spotter Market voice: its prepared lines wait for a free slot when the voice service is busy, instead of dropping.

Spotter Market voices
- A new voice is usable in about 7 minutes. Its everyday calls are built first; the lap-time numbers follow over the next ~20 minutes and arrive on their own. Until then the stock voice of the same type reads lap times.
- Corner names are built only for the tracks you race with corner names on. The first time you drive a track in names mode, that track's corner names are built in your Spotter's voice in about a minute (the stock voice reads them until then), and every driver with that voice gets them.
- Installed voices update themselves: only the new lines download, in the background, and never while you're on track (an update waits until the radio has been quiet for a minute).

FFB Lab
- Spin-aware end-stop guard.
- Strength up to 60 Nm, with a live clipping read.
- Names the program that has taken the wheel.

Also
- Chat avatars stay round instead of stretching down long messages.

Before acceptance:
- Blip page: switch between pages on a Pro account; the Blip page never shows "Meet Blip" or a sign-up screen.
- iRacing Navarra Speed Circuit: Blip names Turn 1, 2 and 3 at the right corners.
- Create a voice: it shows as ready in about 7 minutes and you can pick it. Lap times are read in the stock voice at first, then in the new voice after the background update.
- Corner names on (Coach page), a Market voice selected, drive a track: corner names in the stock voice, then in your voice from the next session.
- FFB Lab on a supervised rig: end-stop guard and strength behave as expected.
- Update from 2.26.200 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.200 - 2026-09-27 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.199 is included.

AI Coach v0.243 - Blip in any Spotter Market voice
- Pro 5× and Pro 20×: every Spotter Market voice is in Blip's voice list (Coach page → Your coach's voice), your own voices first. Pick one and Blip talks in it. Starter and free members see them marked "Pro 5× and Pro 20×".
- Blip's key-up and off-radio clicks follow Blip's volume: turn Blip down and the clicks go down with him.
- When the voice service is briefly busy, Blip's line retries once instead of going silent.

Spotter
- Every Spotter Market voice is in the Spotter voice menu. Pick one and it downloads and becomes your Spotter's voice in one step. Free members see them marked "(paid plans)".
- The Spotter's key-up and off-radio clicks follow the Spotter's volume. Turn the Spotter down and you no longer hear loud clicks around quiet calls.
- Your Spotter voice and Blip's voice are set separately.

Spotter voice studio
- Voices follow your description more closely.
- Flirty, teasing and sultry voices, anime-style voices included. A voice asked for as a child or a teen is made as a youthful-sounding adult and never gets the flirty lines or becomes Blip's voice.

Social voice chat
- Turn voice chat up or down from a wheel dial or buttons, 10% a click.
- Voice chat settings can be changed without joining a channel.

Before acceptance:
- Pro 5× or Pro 20× account: Coach page → Your coach's voice → pick a Spotter Market voice (NORA) → Hear voice, then start Blip and ask a question. Blip answers in that voice, with no silent lines.
- Starter account: the Market voices show in Blip's list marked "Pro 5× and Pro 20×" and can't be picked.
- Spotter page: pick a Market voice you don't have yet; it downloads and the Spotter uses it.
- Turn the Spotter to 10% and Blip to 10%: their clicks are just as quiet.
- Update from 2.26.199 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.199 - 2026-09-27 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.198 is included. Motion anticipation is new and OFF by default; keep motion testing supervised.

AI Coach v0.242 - Blip as your agent, endurance and oval engineer
- Blip changes your motion rig by voice, on track: "less heave", "more braking feel", "motion to 70", "turn the kerbs up", "switch to my Comfort profile", "undo that". Changes are saved to your profile like the Motion page, and land the moment the car is settled (on a straight or stopped), never mid-corner. The rig's safety limits, geometry and wiring stay on the Motion setup page.
- iRacing admin control is on by default for everyone. iRacing itself refuses admin commands from anyone who isn't host or admin of the session. "Clear my black flag", "EOL me" and "wave me by" now happen straight away; anything that touches other drivers or the whole session (yellow, DQ, black flag a rival, kick, pits) still asks one quick question. A question about a flag ("why do I have a black flag?") never clears it.
- Endurance: any race length, including 24-hour races. Multi-stop fuel plans, a stint debrief while the car sits in the pit stall, hour marks (halfway and the final hour named), a pace-fade call when the stint slows, and dusk and dawn.
- Ovals: Blip is your strategist. Tyres over the run (laps on each tyre, lap time lost per lap, what fresh tyres are worth), and at a caution the pit-or-stay call, based on what the cars ahead actually do, a few seconds before your pit entry. Lap-time reads now work on short ovals.
- Blip watches every car: from what iRacing shows of each car (laps since its stop, how long its stops took, its lap-time falloff), the field's tyre falloff and each same-car rival's fuel window. When your own run is short, the field and other TrackPro drivers' data give the tyre read.
- Fuel: caution laps never set your burn, and race pace survives a long yellow.

Spotter - iRacing cautions
- Under caution the spotter names the car to follow: "Follow car 24." At the front: "Follow the pace car."
- "Let car 24 by. It goes ahead of you." when the car you should follow is behind you.
- Free pass, wave-around and "sent to the end of the line", straight from iRacing, and how many laps down you are when an oval caution comes out.
- Lap-by-lap gap change: "Car 24 ahead, 1.2. You took three tenths that lap."

Motion - anticipation (new, off by default)
- Your steering, brake and throttle start the cornering, braking and acceleration cues before the car builds the G, so turn-in and braking arrive earlier. Motion → Advanced → Anticipation (or ask Blip). Start at 60 ms. It learns each car in the first minutes of driving and stays silent until it has. It never leads a slide or a countersteer.

Before acceptance:
- Motion: set Anticipation to 60 ms, drive 2-3 minutes, then feel turn-in and braking. Try 40 and 90. Anything odd: set it to 0 and report it.
- Blip: "less heave" → yes → felt on the next straight; reopen the Motion page to see it saved; "undo that".
- As host of an iRacing session: "clear my black flag" happens at once; "throw a yellow" asks once.
- iRacing oval caution: the spotter names the car to follow; Blip gives the pit-or-stay call before pit entry.
- Update from 2.26.198 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.198 - 2026-09-26 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.197 is included.

AI Coach v0.241 - fuel that just works, and fixes from real sessions
- Fuel knows where you are. In practice, "how much fuel?" gets the qualifying load and the race load. In qualifying or before the green, it gets the race load: the race laps, the pace lap and a spare lap. Once the race is running, it gets fuel to the flag.
- The race length comes from the event, so Blip never asks "how long is the race?" in iRacing.
- When qualifying ends, Blip gives the race load on his own: "Qualifying's done. For the 13-lap race, load..."
- The race briefing says the load instead of "fuel to finish isn't confirmed yet".
- Your practice and qualifying laps plan the race fuel. They are no longer thrown away when the session changes.
- Every TrackPro driver's fuel laps help every driver. With no laps of your own, Blip uses other drivers' laps in this car at this track, then this car's burn at other tracks. It always says where the number came from and errs on the side of extra fuel.
- The load is always rounded up, and the spare grows on long races.
- "Did I lock up?", "did I shift too early?" and "did I spin?" are answered from that moment: the last braking zone, the last upshift against the shift light, and how far the car rotated. Before, Blip answered from what the car was doing right now.
- Venting ("this car is terrible", swearing) gets one calm line, not a lecture. "Trust me" ends a warning for the stint, and "shut up" means quiet.
- A line said to a friend in voice chat ("Sean, can you hear me?") is not answered by Blip. "Sean Skiles" now finds a voice-chat participant listed as "Sean".
- Blip no longer invents features, like "send me a screenshot". For "tell me when to brake" he offers the guided lap, and a bug report reaches the TrackPro team.
- Wheel buttons are spoken as "your wheel button 10", not "fanatec wheel b10".
- A corner call no longer reads "coasting about 0.2s. no coasting —".

FFB Lab
- The Start button works again. From 2.26.195 to 2.26.197 the page found your wheel but Start stayed greyed out, because the core never answered FFB Lab's status request. The FFB overlay's status had the same fault.
- If a session can't start, FFB Lab now says why.

Before acceptance:
- FFB Lab: with your wheelbase connected, Start becomes active and a session starts and stops.
- In practice, ask "how much fuel should I run for the race?": Blip gives the load from the event's race length without asking.
- Run qualifying, then wait for the flag: Blip says "Qualifying's done" with the race load.
- Lock a brake, then ask "did I lock up?": Blip describes the last braking zone, not "brake is at zero".
- In voice chat, say "Sean, can you hear me?" (use a name in the room): Blip stays silent.
- Update from 2.26.197 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.197 - 2026-09-26 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.196 is included. Motion for DCS and MSFS is new in this beta; keep motion testing supervised.

AI Coach v0.240 - fixes from real Blip sessions
- The spoken session debrief no longer reads Blip's internal notes aloud ("Ask calibration (measured, n=9)..."). It speaks only lines meant for you.
- Confirmations no longer loop. If you answer "Clear your black flag?" with anything other than yes or no, Blip asks once more and says "Just say yes and I'll do it." Only a plain spoken "yes" still carries out the action.
- In the garage, "look over my data" no longer reports a stalled engine, no oil or fuel pressure, or an empty tank as trouble. Those are normal engine-off readings while the car is parked.
- Roast mode means it: with roast on, Blip gives trash talk back in kind, swears properly and never scolds you for your language.
- Blip in iRacing: can replay to where you lost time, knows your incidents and iRating, and makes engineer calls in qualifying.
- Blip's answers are no longer cut to a fixed number of words.
- During a server outage, Blip no longer tells you your talk time is used up.
- Custom (ElevenLabs) Blip voices are for Pro 5x and Pro 20x plans. Custom Spotter voices stay on every paid plan, Starter included.
- Listen / Play sample buttons in the Spotter Market, Spotter settings and the Blip voice picker now work whenever the radio is quiet and you are not driving on track.

Flight sims
- Motion for DCS and MSFS (MSFS ships its SimConnect connection).
- Aircraft effects on the motion rig and bass shakers: engines and rotors, runway rumble, touchdowns, landing gear and flap clunks, buffet and guns.

Community
- Member list online, on-track and voice status fixes.
- Reply to direct messages from the email notification.

Before acceptance:
- In the garage, ask Blip "look over my data": no stall, pressure or fuel alarm.
- Say "roast me" and trash-talk Blip: it gives it back, no "that's a bit harsh".
- Ask Blip to clear a black flag, answer with something other than yes, then say "yes": it asks once with "Just say yes" and then does it.
- Finish a session and listen to the debrief: no "calibration" or "n=" numbers are read aloud.
- Update from 2.26.196 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.196 - 2026-09-25 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.195 is included. Motion changes from 2.26.195 still need rig acceptance; keep motion testing supervised.

AI Coach v0.239 - the word highlight follows Blip's voice
- The word Blip is saying is now found in Blip's own voice: TrackPro counts the syllables as they are spoken and matches them to the words on screen. Before, it guessed a speaking speed and fell further behind the longer Blip talked; now it stays with Blip to the end of a long answer.
- Prepared lines (radio checks, corner calls, the opener) are read from the audio file before they reach you and land on the word being said almost every time. Live answers follow Blip as Blip speaks; in a fast run of numbers the highlight can wait for the next pause to catch up.
- Lap times, gaps, units and codes are read the way Blip says them ("1:47.3", "0.4s", "GT3", "T12", "km/h").
- When the coach speaks a language other than English, the words show without a highlight rather than a wrong one.
- Blip's voice is measured on a separate, silent audio path, so the highlight never touches how Blip sounds.

Before acceptance:
- Listen to a long answer from Blip and a prepared line (the opener): the highlight stays on the word being said, start to finish, on your usual headset. Try a Bluetooth headset if you use one and note whether the highlight is ever ahead of the voice.
- Interrupt Blip mid-answer with push-to-talk: the next answer's highlight starts on its first word.
- Update from 2.26.195 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.

## TrackPro V2 2.26.195 - 2026-09-25 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Everything in 2.26.194 is included. Motion changes a lot in this beta (see Motion); keep motion testing supervised until the rig checks at the end pass.

AI Coach v0.238 - meet Blip
- The AI Coach is now Blip and introduces himself that way. The coach overlay is Blip: a live helmet whose face follows the real coach (starting, listening, thinking, talking), with his actual words in one box and the word he's saying highlighted in TrackPro blue.
- Blip reacts to what really happens on track: a clean new best, real passes, incidents and his finish. He gets to know each driver: shy at first, cheekier as you drive together, and he greets you when you start him.
- When Blip says he'll check something, he now follows up, or tells you he couldn't.
- Blip answers questions with no sim running instead of asking you to start one.
- Humor: Roast me now swears and goes mean, and trash talk gets answered in kind. New switch: "Coach can swear".
- If your saved speaker is missing, Blip plays on the Windows default output with one warning and moves back when your headset returns. Choosing a mic no longer replaces the speaker you picked.
- Comparisons against the fastest lap count a lap you just banked right away, and the glitch guard no longer flags a genuinely fast driver.
- Blip's settings: push-to-talk and headset at the top, then three small sections instead of one long fold. Radio Check fits its card.

Blip acts for you
- Blip asks before he changes anything. Only a plain yes or no that you say, heard on the PC, confirms a change. "Done." comes once iRacing shows it.
- Pedal and motion changes now work on track too: a pedal change waits until you lift off that pedal, a motion change until the car is settled.
- Standing orders in iRacing: "tell me when car 12 pits", "box when the window opens".
- "Sort my stop" asks one question for the whole stop. In iRacing races Blip offers fuel to the finish when you're short, and repairs when there's damage.

Blip's page
- Your week at the top: grades, streak and weekly mission, Blip's latest radio words, and Start Blip.
- Weekly mission: five laps within 0.5% of your best from before this week, on a car and track you've driven before, earns one Race Pass tier (1,000 XP) once a week.
- Pick a car and track: your best and next target, your last visit, one focus, and a track map with every corner coloured by how well you've mastered it. Open a corner to compare your best pass with your usual one, see what to change, and ask Blip about it.
- Your skills over time: braking, throttle, consistency, pace and control, each with its history, plus your biggest gain and your weakest skill.
- Drivers without a plan get a page to try Blip: time found in their own corners, real radio calls from Blip, and one free question.

AI Coach monthly limits
- Starter: 12 minutes of talk and 100 typed messages (up a third). Pro 5x is exactly five times Starter and Pro 20x exactly twenty times. Every plan has a monthly limit; nothing says unlimited any more.

TrackPro on your phone
- Pair your phone in Settings > Pair TrackPro Mobile. The phone shares Blip's conversation and your practice focus, and shows the desktop Pedals, Haptics and Motion pages at phone size, with an E-Stop always on screen.

Spotter
- The Spotter has its own sidebar entry, page and chatter level, separate from Blip. "Spotter, talk less" goes to the Spotter only. Switches that changed nothing were removed; the rest do exactly what their rows say.
- Assetto Corsa and ACC: cars running door to door are now called, and cars in the pit lane or across a hairpin are no longer called alongside.
- New Language setting for the Spotter's reactions: Clean, Salty (swearing) or Unfiltered (swearing plus cheeky innuendo). 18+ confirmation first. Traffic calls and flags never change.
- Spotter voice creation works end to end: describe any voice and it's matched in style, always as an adult's voice. Your own voices show in the voice menu with build progress, then one click to download and use them.
- Market cards show voice type, pace and energy with a race-radio sample, and the Market filters by voice type.
- The voice sample plays on the Windows default output when your saved headset is missing.

Motion
- Motion is now two pages. Motion is for driving and feel: on/off, overall strength, pick a feel (Omega Comfort / Omega Full), Braking, Cornering and Bumps with live bars and - / +, and a live view of what each actuator is told. Everything about the hardware is on Motion setup (top right): controller and connection, rig dimensions, corner wiring, moving the rig by hand, the response test and diagnostics.
- Move the rig by hand: pitch, roll and heave sliders (-100% to +100%) plus "all the way" buttons, to check clearances. The rig moves slowly, holds, and returns to center after 2 minutes without a change or when you leave the page.
- Advanced tuning shows what your rig can physically do (from the actuator rating and your rig dimensions) and what your profile delivers. Controls that never reached the rig were removed (LP Freq, Tilt Coord, Max Tilt, Slew Rate, the 360 Hz checkbox); 360 Hz playout is always on. Omega profiles get Restore factory settings.
- New response test (Motion setup): your phone strapped to the seat frame measures the real angles at full travel, the delay from TrackPro's command to the seat, how fast braking and cornering cues arrive and, optionally, how much vertical acceleration the actuators follow. Each run is saved to %APPDATA%\TrackPro\motion-response\. Needs TrackPro open on the paired phone.
- Quieter actuators: every frame to the Thanos controller is now sent fresh on an even cadence (repeated frames made the servos stutter audibly), and actuator road texture stays below 25 Hz.
- TrackPro reads the Thanos 4U settings on connect and logs any drift from the rig baseline.
- Rig dimensions: usable stroke must match the Stroke setting on the Thanos controller.

Force feedback
- Assetto Corsa's own FFB is switched off automatically while TrackPro FFB is on, and restored afterwards. iRacing's FFB is shown live ("IRACING FFB ON" on the FFB overlay); switch it off in iRacing yourself for now.
- Compact FFB overlay: power, strength - / +, and an output meter that shows clipping.

Overlays
- The Overlays page: pick an overlay from one list and edit it with a live preview beside it; display setup sits top right.
- VR overlays are back as an opt-in add-on on the Overlays page. Turning it on takes one Windows permission prompt; when it's off, nothing loads into your games. A setup guide checks your OpenXR runtime and OpenComposite. Supported: iRacing in OpenXR mode, Le Mans Ultimate 1.4+, and ACC, AMS2, AC and rFactor 2 through OpenComposite.

Driver Progress
- Pace trend from your saved laps, back to your first session.
- Weekly report card: grades for pace, consistency and seat time that reset every Monday, a weeks-in-a-row streak, this week's personal bests and a next target. Also on the Report Card page.

Updates
- Smaller, faster updates: stock spotter clips ship compressed, and the remote support engine downloads only when you open Remote Support. The installer closes TrackPro's engine cleanly instead of waiting on fixed timers, and an update no longer counts as a crash.
- Update prompts stop nagging: "Later" on a stable update is remembered for that version, and prompts wait while a sim is running.

League Night
- TrackPro records your iRacing identity with each race, so league results are matched to you by name and car. Friday drivers should be on this version.

Other fixes
- The lap-save warning no longer counts laps the retry queue already saved, and its "Run diagnostics" button starts the run.
- Title bar labels show whenever they fit.
- Spanish: corrected translations, and the remaining English text is translated.

Not switched on yet
- Typed chat with Blip (his page and the phone) picks up his name and the new swearing and roast settings with the next coach server update. The radio has them now.
- Blip's prepared radio lines recorded in his live voice are ready in the app; they turn on from the server one voice at a time.

Known in this beta
- The phone shows the desktop pages at phone size; phone layouts come later.
- ACC can still call a car in a pit lane that runs closer than 10 m to the track (ACC gives no pit flag for other cars).

Before acceptance:
- Blip in a real session: reactions, the word highlight on your headset, and unplugging and replugging the headset mid-session.
- Ask Blip for a pit change and a pedal change on track; answer yes and no. Check "Done." and that the pedal change waits until you lift off.
- Try the free question on Blip's page with an account that has no plan.
- Update from 2.26.194 with the in-app updater: TrackPro closes, installs and restarts cleanly, and pedals work afterwards.
- Spotter on a headset: the stock clips sound right, and door-to-door calls in AC and ACC.
- Motion: run the response test once with a rider and keep the saved file; check the hand moves and actuator noise.
- VR overlays on a real headset. Pair a real phone and try its E-Stop.
- On Blip's page, check the corner markers sit on the real corners on a few tracks.

## TrackPro V2 2.26.194 - 2026-09-23 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Motion changes from 2.26.188 are included unchanged and remain on validation hold until physical Thanos4U acceptance passes. Everything in 2.26.193 is included.

AI Coach v0.237
- The AI Coach now has its own version number, shown in Settings and on the Coach page. This release is AI Coach v0.237.
- "Where am I losing time to the fastest lap?" now works on every car and track with laps in TrackPro. The coach compares you against the fastest clean lap from any driver and says where the time goes, corner by corner. It never names the other driver. Before, it could only use laps from drivers who had turned on lap sharing.
- The coach's comparisons no longer need lap sharing, and the coach no longer asks you to turn it on.
- Honest answers at the edges. If you're the only driver with laps there, the coach says so instead of praising you. If a lap's telemetry doesn't load, it gives the time gap and says the corner breakdown didn't load. A best lap far quicker than everyone else's is treated as a timing glitch, not a record.
- New setting: "Use my laps in AI Coach comparisons" (Settings > Sharing, and Coach settings). It's on by default. Turn it off to leave your laps out of other drivers' comparisons; you're still compared against theirs.

Sharing
- "Share telemetry laps" now controls what other drivers see by name: overlaying your laps on the Telemetry page and racing them as in-sim ghosts. It also still decides whether your laps count toward Setup Shop's fleet setup data. It doesn't affect the AI Coach.

Beta updates
- The download bar now matches the percentage shown, and starting the same update from the prompt and from Settings no longer runs two downloads.

Known in this beta
- Creating a spotter voice cannot make samples yet ("Couldn't make samples right now") while the voice service is being connected. The market stays empty until the first voices are built.

Before acceptance: rehearse the AI Coach demonstration on the target rig with the real headset, simulator and recording software. In the Ferrari 296 GT3 at Red Bull Ring, after four clean laps, ask "Where am I losing time to the fastest lap?" and check the named corners against the lap.

## TrackPro V2 2.26.193 - 2026-09-23 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Motion changes from 2.26.188 are included unchanged and remain on validation hold until physical Thanos4U acceptance passes. Everything in 2.26.192 is included.

AI Coach
- Coach memory is live. The coach can save what it learns about you (goals, how you like to learn, what works for you) across every car and track, and the "What your coach remembers" panel in Coach settings loads your memories. The service side was switched on after 2.26.192 was published, so 2.26.192 benefits too.

Spotter
- Spotter Market voices install into their own folder for each version, so updating a voice never touches the copy the Spotter is using.
- Updating or removing the voice the Spotter is speaking in waits until the radio is off.
- "Update" appears only when the market has a newer version of a voice.

Known in this beta
- Creating a spotter voice cannot make samples yet ("Couldn't make samples right now") while the voice service is being connected. The market stays empty until the first voices are built.

Before acceptance: rehearse the AI Coach demonstration on the target rig with the real headset, simulator and recording software, including "Remember that..." and the memory panel.

## TrackPro V2 2.26.192 - 2026-09-23 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Motion changes from 2.26.188 are included unchanged and remain on validation hold until physical Thanos4U acceptance passes. The 2.26.191 candidate was never published; everything in it and in 2.26.190 is included here.

AI Coach
- When you say you are nervous or frustrated, the coach responds to that first, gives one calming step, then one simple focus, instead of opening with technique.
- "Remember that...", "note that..." and "don't forget..." now always save a coaching note for this car and track, then confirm.
- Damage questions are answered from what the car reports: repair times, warnings and tire wear. The coach no longer says "no damage" when the data cannot show it.
- Corner gear comparisons no longer swap your gear and the reference lap's gear.
- A greeting with a question ("Hey Jim, how was that session?") gets the question answered, and a queued "I can't hear you" is never played once the coach has heard you.
- The coach speaks only in your selected coach voice, and the spotter only in its selected voice pack. The Windows fallback voice is removed, a voice change never plays audio prepared in the old voice, and the coach and spotter can no longer share a voice.
- New: coach memory. The coach can remember your goals, how you like to learn and what works for you, on every car and track. Coach settings has a "What your coach remembers" panel to view, add or forget memories, or delete them all, and a switch to turn memory off. Only you can see it.

Setup Shop (Starter and up)
- New: TrackPro AI setups for iRacing, built from the setups TrackPro drivers run fastest on the same car and track. A TrackPro AI setup is never a copy of any one driver's setup.
- Setup Shop > TrackPro AI follows the car and track loaded in iRacing and shows each value beside your current one. "Use this setup" starts a garage checklist that ticks off live as you set each value. Save it with the suggested name and it is labelled TrackPro AI in My garage.
- After three clean laps on it, Setup Shop compares your best three laps with your previous best at that car and track. The AI Coach can talk you through the remaining values one at a time.

Spotter
- New: Spotter voice studio and Spotter Market (Coach > Spotter settings). Describe a spotter voice, hear samples and build a full voice pack. Starter and up can download any pack from the market; free members keep the stock voices.
- Lap-time readback: 81 takes that stood out from the rest of their voice (harsher, off-pitch or quieter) were regenerated in the two stock voices. Silent, stalled and slow traffic, number and lap-time clips were also replaced.

Reliability and performance
- If TrackPro's display process crashes, the page reloads itself, and after a graphics crash the window repaints instead of staying black. If the WebView2 runtime fails, TrackPro restarts (at most once every 10 minutes).
- Community member lists and the Race Pass prestige animation do far less rendering work.
- Crash and freeze reports carry more detail for support: window focus, the active game and the previous session's handle count.

Account
- A PC left on the "account active on another PC" screen no longer takes the account over by itself, for example from an event rig that lost its internet. Taking over always needs a click, and a running PC that loses the account to an automatic claim takes it back. The screen also offers "Sign in with a different account".

Motion
- The 3D rig view is removed from the Motion page.

Known in this beta
- Creating a spotter voice cannot make samples yet ("Couldn't make samples right now") while the voice service is being connected. The market stays empty until the first voices are built.

Before acceptance: rehearse the AI Coach demonstration on the target rig with the real headset, simulator and recording software; listen to the lap-time readback in both stock voices on a headset; run one TrackPro AI setup checklist in the iRacing garage.

## TrackPro V2 2.26.190 - 2026-09-22 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Motion changes from 2.26.188 are included unchanged and remain on validation hold until physical Thanos4U acceptance passes.

AI Coach
- Fixed the coach going silent after some actions and checks (about 1 in 8 in field data): a refused reply after a completed tool is now retried for the same question, without cutting off audio.
- A volume level you name ("spotter volume 60", "set your volume to 80") is now applied exactly. Relative requests ("turn it down", "10 percent quieter") still move from the current level.
- Includes everything in 2.26.189.

Before acceptance: rehearse the AI Coach demonstration on the target rig with the real headset, simulator and recording software.

## TrackPro V2 2.26.189 - 2026-09-22 (beta)

BETA: for supervised testing. Automatic updates stay on the existing stable release. Motion changes from 2.26.188 are included unchanged and remain on validation hold until physical Thanos4U acceptance passes.

AI Coach
- Cues and answers are grounded in the latest measured evidence; the coach recognizes demonstrated pace without inventing limits.
- A beginner or short practice plan with no measured laps gives a useful general exercise instead of guessing specific corners.
- Corrected track map identity, answer evidence and headset recovery after a device change.
- Corrected fuel advice, with briefings when the session changes.
- New out-lap preparation briefings for practice and qualifying.
- Coach voice and banter stay consistent across every audio path.

Other
- New in-game TrackPro FFB strength and power overlay.
- Community chat: history, delivery recovery and timestamps fixed.
- Setup capture evidence qualification repaired.

Before acceptance: rehearse the AI Coach demonstration on the target rig with the real headset, simulator and recording software. Motion acceptance requirements from 2.26.188 still apply.

## TrackPro V2 2.26.188 - 2026-09-16 (beta, validation hold)

VALIDATION HOLD: for supervised testing only, not approved for customer delivery. Physical Thanos4U acceptance and PC/controller power-cycle testing remain pending. Automatic updates stay on the existing stable release.

- Includes public Thanos4U / four-actuator 3DOF setup, saved strength and axis assignments, faster channel identification, and center-only software startup from 2.26.187.
- Saved hardware settings and controller selection use flushed replacement files and a valid recovery copy. Corrupt or unreadable saved data cannot silently become default motion settings.
- Startup restores the acknowledged native motion snapshot, protecting against partial browser-storage writes. Setup and Connection help wait for the core to confirm the controller selection was saved.
- A failed controller enable stays disabled. Stop during startup prevents a pending restore from re-arming motion.
- Opening the Thanos port no longer sends center-position packets. A lost connection cancels motion/tests and requires an explicit Enable to resume.
- Corrects the Thanos command interpretation against the manufacturer's manual: spike-filter commands are not motor enable/stop commands. TrackPro preserves controller tuning; homing, startup, physical travel and offline parking remain controlled by the configured firmware.
- Software E-stop cancels pending output and closes the Thanos stream instead of sending an undocumented command or a sudden center target. This does not cut servo power or prove the actuators have stopped. The physical E-stop remains necessary for hardware emergencies.

Before acceptance: verify the installed controller firmware, controller-side stroke and filter configuration, physical E-stop, channel directions, actual travel and timing, saved setup after app/PC/controller restart, and an installer upgrade that preserves settings. Do not promote this candidate based on software tests alone.

## TrackPro V2 2.26.187 - 2026-09-16 (beta, validation hold)

VALIDATION HOLD: 2.26.187 is not approved for customer delivery. Further audit found settings-recovery and controller-command issues. A replacement must pass software checks and supervised Thanos4U acceptance before promotion. Automatic updates remain on 2.26.181.

- Motion is available to everyone without an access code, directly in the sidebar.
- Setup supports Thanos4U with four lift actuators for 3DOF: pitch, roll and heave. ESP32, standalone AMC, and unfinished 5DOF/6DOF layouts are not selectable.
- Controller, USB binding, corner assignments, rig measurements and profile tuning are saved on this PC. A native settings backup restores them if an update resets browser storage; save errors remain visible.
- Overall strength controls real motion output and is remembered per profile.
- Identify each controller channel in 2 seconds, label it while moving, then choose Found it to return and continue to the next channel.
- Normal startup moves to center without the repeated full-stroke check. A manual full-travel check remains in My rig.
- Supported setup range: 50-150 mm usable stroke, with a configurable command speed ceiling within the actuator rating (up to 250 mm/s).

Beta acceptance: software regression checks pass. Physical Thanos4U startup, axis direction, travel, E-stop, and overnight/power-cycle checks remain pending on the delivery rig. This beta is a signed download; it is not yet offered by the stable automatic-update feed.

## TrackPro V2 2.26.186 - 2026-09-13 (beta)

- Spotter and coach lap times are exact: both wait for the sim's official time for that lap (up to 5 s) and stay silent rather than read the previous lap. iRacing read one lap behind on most laps before.
- The coach invites the driver to talk: offers on lap notes until the driver speaks, one short question after a scrappy practice lap, and a rotating "Try asking" line on the Coach page.
- Rival comparison against any driver in the session by name, car number or position, TrackPro user or not, from observed sim data; only observable causes are spoken.
- The coach never says it can't: 41 refusal lines rewritten as what she has, what gets the rest, and when.
- An iRacing UI left open with the sim closed is no longer treated as a detected sim.

## TrackPro V2 2.26.185 - 2026-09-12 (beta)

- Coach humor register: Professional, Some fun (default) or Roast me, under the coach voice picker; "roast me tonight" on the radio saves it.
- Coach speaks at least once per practice lap when nothing else was said, once per two race laps, never in a battle or near a press-to-talk.
- Coach never announces a reconnect: lost acknowledgements are probed before any teardown, reconnects prefetch token and speaker, "Back with you" removed.
- Live coaching on any track: with no trusted map the coach measures corners from three clean laps and coaches live from them.
- Rival comparison against nearby cars never requires a friendship; observed traces survive session info updates and reconnects.
- Cedar and Marin are the setup voice defaults; the welcome radio check uses the live coach voice.
- Fuel context carries the driver's unit; "clear my black flag" refers to the driver's own car.
- An iRacing UI left open with the sim closed is no longer treated as a detected sim.

## TrackPro V2 2.26.184 - 2026-09-12 (beta)

- Motion no longer disconnects and parks on a brief host stall. The Thanos writer re-sends for up to 250 ms before treating the port as gone; a genuine port loss still disconnects.
- A new host stall report ties pedals, the virtual joystick driver and the motion port together when they freeze at the same moment, with the number of TrackPro core processes alive.
- Spotter proximity calls keep one voice: a repeated call reuses the same take, reminders come every 2 seconds (was 1), and a call never restarts itself mid-word. First side calls and every clear stay immediate.
- Spotter transmissions key off with the radio squelch. New "Radio clicks" toggle under Radio effect.
- Spotter radio voicing is softer and consistent from call to call; every number fragment is level-matched.
- Lap times are read like a spotter: "Last lap, one oh six, three sixty-six", about 3.3 seconds instead of 11.
- Setup Shop detects the live car and track without waiting for device status and clears the previous car's garage sheet on a car change.

## TrackPro V2 2.26.182 - 2026-09-11 (beta)

- Live Coach removes sentence-count and word-count cutoffs so healthy spoken answers can finish. Long custom-voice replies preserve their remaining text through the final segment.
- Starter now uses the same live AI model, coaching tools and knowledge as Pro. Your plan's usage allowance still applies.
- AC practice on layouts without a reliable corner map starts with a clear explanation and offers measured clean-lap consistency feedback. More laps are no longer presented as a way to unlock an unavailable map.
- Incorrect map matches are rejected when the layout length does not fit. Corner names and braking points are not guessed.
- Lap counting handles the simulator's counter and position arriving separately. Incident laps are excluded from clean-lap comparisons, and busy or failed feedback can retry.
- Guided acceleration instructions leave time for the voice to start before their reference point.

Automated validation replayed 38 recorded laps and captured a complete 144-second spoken answer through the playback code. Physical headset routing, live-provider delay and ACC field acceptance are not certified by those checks.

Known limitation carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target.

## TrackPro V2 2.26.181 - 2026-09-11 (stable)

- Live Coach preserves slower transcriptions of acknowledged speech without delaying normal replies. Late commands still cannot affect a later question.
- A held PTT re-key can wait for the previous question to finish. Releasing the button cancels it, and connection startup avoids repeated offline rejection warnings.

Promoted from the signed beta without rebuilding the installer. Headset/driving and physical hardware acceptance remain pending; no measured end-to-end latency improvement is claimed.

Known issues carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target. Physical Haptics and Omega motion acceptance, including the secondary heave tail, remain pending.

## TrackPro V2 2.26.180 - 2026-09-11 (beta)

- Haptics becomes a compact mixer with all 12 effects visible. Each row holds the enable switch, strength, activity, Test and Tune. Frequency and priority controls expand below the selected effect. Overall strength uses one line; setup, presets, mix priorities and saved car profiles remain available with less wasted space.
- Saved haptics settings, channel routing and synthesis behavior are preserved. The mixer adapts to narrow windows and keeps unsupported effects disabled with their explanation available.
- Personal Warranty now explicitly filters claims to the signed-in owner, including admins. This fixes shipping requests made from another customer's claim accidentally displayed on the personal page. Admin claim management remains available separately.
- Warranty requests show the server's explanation or readable guidance instead of a generic Edge Function error. Missing Spanish labels for the latest Coach and Spotter settings are included.

Beta testing: verify saved Haptics setup and shaker output on your rig, plus Warranty in the installed app. Physical hardware acceptance and live carrier rating remain pending.

Known issues carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target. Headset/driving acceptance of the previous Coach audio changes and physical Omega motion acceptance, including the secondary heave tail, remain pending.

## TrackPro V2 2.26.179 - 2026-09-10 (beta)

- OpenAI Live Coach gains conversational delivery instructions and gentler audio processing to preserve vocal warmth and dynamics. Existing session brevity, tool use and verified-data rules remain in place.
- Coach and Spotter have independent voice controls, with OpenAI Coach previews including Marin and Cedar. Saved voice choices are preserved. Nari is not enabled.

Beta testing: compare headset sound with the Coach radio effect on and off, then check three flying practice laps, pre-corner timing, progress feedback, HUD off, PTT interruptions and recovery. Sound quality and live driving validation remain pending; no measured latency improvement is claimed.

Known issues carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target. Physical Omega motion acceptance and the combined hill/braking/crest secondary heave tail remain pending.

## TrackPro V2 2.26.178 - 2026-09-09 (beta)

- Motion includes Omega Comfort at 45% intensity and Omega Full at 65%. Both provide the same complete pitch, roll, heave and actuator effects, including suspension impacts, engine, shifts, curbs, road, ABS and traction cues.
- Confirming My rig setup prepares both matching Omega profiles. Controller selection, dimensions and confirmed cable labels persist across profile switching and restarts. Custom tunes and different saved rigs are preserved; unconfigured Omega profiles require setup before enabling motion.
- Motion gains faster body response, stronger elevation and suspension cues, smoother startup, and bounded Thanos controller recovery. The coordinated motion trial remains a separate developer experiment.
- Haptics gains clearer effect controls and updated seat-feel presets. Compact windows fit navigation and content more reliably.

Beta testing: confirm setup persistence, both Omega intensities, pitch/roll/heave, telemetry-driven effects, stop/re-enable and controller reliability on the actual rig. Physical acceptance of the stronger tune and intermittent-disconnect fix remains pending. Combined hill, braking and crest cues can produce a secondary heave tail.

Known beta issue carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target.

## TrackPro V2 2.26.177 - 2026-09-06 (beta)

- Wheel Studio adds a device-definition library with import, validation, preview, export, and removal. Compatible HID and serial devices can describe separate RPM, warning, button, and encoder LED banks, including grouped or reversed wiring.
- Displays have their own device inventory and explicit selection. Supported VoCore panels use firmware identification for their dimensions, and native USBD480 output is added. A disconnected selected screen cannot redirect output to a different display.
- Racing dashboards gain clearer timing graphics, indicators, and fitted landscape and portrait layouts. Display choices show supported products and output availability.
- LED hardware checks show addressable banks and individual lights. Quick assignments cover RPM, flags, ABS, TC, proximity, pit limiter, and backlighting while preserving existing effects. Stop controls release LED and dashboard output.
- Settings gains searchable categories and clearer recording, privacy, audio, installed-version, and beta controls. Video recording starts off after this upgrade until you explicitly enable it again.
- Privacy controls require account confirmation and remain accessible without a paid Coach plan. Delayed settings reads and audio-device detection preserve confirmed privacy choices.
- Stream Deck integration and its bundled plugins have been removed.

Beta testing: verify physical LED bank mappings, screen selection/orientation, VoCore and USBD480 output, headset/PTT, and recording off/on on your rig. Universal wheel coverage and physical hardware sign-off remain incomplete. True wheel-lockup LED telemetry is not yet available.

Known beta issue carried forward: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target.

## TrackPro V2 2.26.176 - 2026-09-05 (beta)

- Support gains saved account-linked cases, guided troubleshooting, suggested replies, and repair verification. Reopen earlier conversations and send a reviewed case to the team when human help is needed.
- Live telemetry is shared across app views to reduce repeated processing. Hardware pages clean up their listeners more reliably, with improved reconnect and shutdown handling.
- Onboard recording is opt-in and uses continuous segmented video when enabled. Long sessions preserve lap telemetry and video alignment, with background uploads and retention that protects saved highlights.
- Coach references use anonymous, measured corners matched to your exact sim, car, and layout. Opponent lap answers use observed lap times, and public lap/ghost sharing respects both drivers' choices.
- Wheel Studio adds new racing dashboards, landscape and portrait layouts, clearer instruments, and shared fuel estimates.
- Event Mode retries, Setup Shop comparisons, and app navigation receive further cleanup.

Beta testing: check long stints with recording off and on, Coach/PTT and headset audio, wheel displays, and support repairs on your rig. Physical hardware and live driving sign-off remain pending.

Known beta issue: text Coach may suggest a slower community corner when your own faster corner is private. Live Coach keeps your faster personal target.

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
