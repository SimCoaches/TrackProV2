# TrackPro V2

TrackPro V2 is the Sim Coaches Windows app for sim racers who want one place to set up their hardware, review laps, watch onboard video, compare telemetry, and manage their racing data.

## Download

Download the latest signed installer from the [TrackPro V2 releases page](https://github.com/SimCoaches/TrackProV2/releases/latest).

TrackPro updates are delivered through this public release channel. The app checks the latest release, shows the changelog, downloads the signed installer, applies the update, and restarts.

Latest stable release: TrackPro V2 2.26.266.

Beta [2.26.279](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.279) fixes freezes in races (lap ends no longer pause TrackPro's window, and after a race the window no longer falls behind the sim's data) and a sign-in that could lapse after a long freeze, adds Turn lock to lock to Blip's steering setup, and the Setup Shop server update is live (Blip v0.280). Includes 2.26.278. Supervised testing only; the freeze and sign-in fixes haven't been tried in a race yet.

Beta [2.26.278](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.278) makes Blip's steering setup work with iRacing's calibration (exact 90° and 30° turns), lets your own wheel steer through TrackPro whenever Blip isn't driving, labels Blip's spins and offs for its learning, kicks every truck gear and judges Setup Shop setups by same-session A/B laps (Blip v0.280). Includes 2.26.277. Supervised testing only; none of it has been tried on a rig yet, and the Setup Shop changes wait on a server update.

Beta [2.26.277](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.277) grinds the gears on a truck's motion rig and shakers when American Truck Simulator or Euro Truck Simulator 2 refuses a shift, keeps the shift kick on slow truck shifts, keeps laps Blip drove out of your coaching and gets Blip going again after a spin (Blip v0.280). Includes 2.26.276. Supervised testing only; the truck changes and Blip's recovery still need a check on a rig.

Beta [2.26.276](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.276) starts the brain call's fair test: one brain call in four, chosen at random, is held back so the staff Brain page can measure whether the calls make drivers faster (Blip v0.279). Includes 2.26.275. Supervised testing only; the fair test hasn't run on a rig yet.

Beta [2.26.275](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.275) lets Blip drive in offline iRacing AI sessions as well as a solo Test Drive, where it had refused with "2 cars are in the session" (Blip v0.278). Includes 2.26.274. Supervised testing only; Blip doesn't see other cars yet, and Blip driving still needs a check on a rig.

Beta [2.26.274](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.274) moves the data that grows with every race and setup change out of the app's small local storage, so a full storage can no longer crash the app (Blip v0.278). Includes 2.26.273. Supervised testing only; Blip v0.278 and the paint fixes still need a check on track.

Beta [2.26.273](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.273) adds the staff AI Designer to Paint Studio, makes Paint Studio work for every car iRacing lets you paint (including clear windows on cars with paintable glass), and has Blip coach with references to aim for (Blip v0.278). Includes 2.26.272. Supervised testing only; Blip v0.278 and the paint fixes still need a check on track.

Beta [2.26.272](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.272) adds a staff garage pass for proving each car's camber, toe, ride heights and caster from iRacing's own setups, and stops a full local storage from crashing the app (Blip v0.277). Includes 2.26.271. Supervised testing only; the garage pass hasn't been used in the app yet.

Beta [2.26.271](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.271) keeps the seat quiet in the pit box until the engine is running: in iRacing an engine that's off no longer buzzes the seat or grows with the throttle, and the engine-start knock now plays there (Blip v0.277). Includes 2.26.270. Supervised testing only; the haptics still need a rig check.

Beta [2.26.270](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.270) engineers TrackPro AI setups from how the car handles: every session reports understeer, oversteer, bottoming and wheelspin, and the setup engineer changes the setup the way a race engineer would, keeping a change only when the handling gets better (Blip v0.277). Includes 2.26.269. Supervised testing only; the handling reports still need a rig check.

Beta [2.26.269](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.269) adds qualifying, race and endurance setup files that load the fuel the distance needs, reads iRacing's own setups in every installed car, keeps saved haptics profiles safe from presets, and adds car setting boxes you tap to cycle on the dashes (Blip v0.277). Includes 2.26.268. Supervised testing only; the new setup files still need a check in a real garage.

Beta [2.26.268](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.268) lets Blip run the iRacing admin and chat commands you ask for on the radio, calls the coach Blip everywhere in the app, and brings the seat alive in the pit box, with a knock when the engine starts (Blip v0.277). Includes 2.26.267. Supervised testing only; the admin commands still need a hosted-session check and the haptics a rig check.

Beta [2.26.267](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.267) makes Ambient lighting work without setup: no Advanced settings, a colour for each racing alert, car alongside on the left or right per light, a Screen choice that follows the game or keeps the screen you pick, and the view ahead read on every screen setup (singles, TVs, every ultrawide, triples), with sharper shadows (AI Coach v0.276). Includes 2.26.266. Supervised testing only; the lights still need a check on real triples and super-ultrawides.

Earlier beta builds, all included in 2.26.266 (their notes describe each build as it was tested):

Beta [2.26.265](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.265) lets any phone or tablet on the same Wi-Fi show a live dash (Wheel Studio > Phone & tablet) sends dash frames as the game makes them, and turns motion off fast when a game sends a stuck, impossible value (AI Coach v0.276). Includes 2.26.264. Supervised testing only; the tablet dash still needs a check on real devices.

Beta [2.26.264](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.264) stops one big bump from turning motion off for the session, makes Road Texture felt on iRacing and lets every haptic driving effect reach the shaker's full stroke at 100% in the Optimized mix, has the ambient lights follow the view out of the car (darker in shade, tunnels and at night, no pedal flashes, automatic two-step setup) and adds a brightness slider for wheel LEDs and button lights (AI Coach v0.276). Includes 2.26.262. Supervised testing only; the motion, haptics, ambient and LED changes still need rig checks.

Beta [2.26.262](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.262) makes motion follow the game by itself: ATS Truck on ATS and ETS2, your last Omega profile on every other game, with smoother Omega Comfort and Full defaults (AI Coach v0.276). Includes 2.26.260. Supervised testing only; the switching and the new defaults still need checks on more rigs.

Beta [2.26.260](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.260) makes the truck games lean through a whole turn: the game reports no acceleration in a steady corner, so TrackPro now adds the turn itself (speed times yaw rate) and the lean holds and grows as you turn harder. Includes everything in 2.26.259.

Beta [2.26.259](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.259) signs the ATS / ETS2 plugin so Windows Smart App Control lets the game load it: on PCs where 2.26.258 showed the truck plugin as installed but sent no data, truck motion works again. Includes everything in 2.26.258.

Beta [2.26.258](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.258) stops the sudden motion jolts on 60 Hz games such as the truck games, gives the ATS Truck profile gentle limits you can see and change, adds a Gear shifts control, and makes every motion control do what it says (AI Coach v0.276). Includes 2.26.256. Supervised testing only; the truck motion still needs a check on a real rig.

Beta [2.26.256](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.256) smooths the truck cab sway: the seat follows the cab like a damped spring, keeping the sway and leaving out the cab's quick wobble that made it shake (AI Coach v0.276). Includes 2.26.255. Supervised testing only; the truck sway still needs a check on a real rig.

Beta [2.26.255](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.255) makes the motion seat follow the truck's cab sway in American Truck Simulator and Euro Truck Simulator 2, raises Thanos rigs left at the old 50 mm/s setup speed to their actuators' rating, plays iRacing force feedback on the sim's own clock, adds a one-shaker BST-1 kit to haptics, and lets Ambient lighting follow the game's screen by itself (AI Coach v0.276). Includes 2.26.254. Supervised testing only; the truck sway and the force feedback timing still need checks on real rigs.

Beta [2.26.254](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.254) makes motion strong again: braking, throttle and cornering keep their travel at any strength and borrow what the track's shape is not using, road camber no longer leans the rig, and on race tracks the rig levels out when the car stops. It also adds American Truck Simulator and Euro Truck Simulator 2 motion and Blip's six-voice list (AI Coach v0.275). Includes 2.26.253. Supervised testing only.

Beta [2.26.252](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.252) lets drivers choose the lap Blip coaches them against, adds brake-board coaching and a fix after any corner that cost a tenth, records track conditions on every lap, brings RPM tables, up to 200% strength and a real shift thud to haptics, shows every flag and faster traffic on wheel side lights, and puts the AI setup into iRacing with one click in Setup Shop (AI Coach v0.273). Includes 2.26.251. Supervised testing only; haptics feel and side lights still need hardware checks.

Beta [2.26.251](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.251) opens LEDs & Dash to every driver from the left menu, turns wheel LEDs and dash screens off while the PC sleeps or shuts down, lays out the SIMDID DV480 lights in a GT layout, stops Ambient lighting glowing brake red on a parked car, and gives the Support assistant new checks for pedals, devices, microphone, lap saving, sim telemetry and installs (AI Coach v0.272). Includes 2.26.250. Supervised testing only; the SIMDID changes still need checks on real hardware.

Beta [2.26.250](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.250) draws every dash flag as the real flag (a true checkered board, the meatball, the blue flag's stripe) on the wheel, overlay, studio and monitor dash, drives standard serial LEDs such as the SIMDID DV480 the way those devices expect, keeps earlier sessions' results and the starting grid on the monitor timing board, and refines the Optimized seat haptics and Ambient lighting (AI Coach v0.272). Includes 2.26.249. Supervised testing only; the serial LED change and the flags still need checks on real hardware.

Beta [2.26.249](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.249) makes Optimized the default seat haptics mix for new profiles: every effect in its own frequency range for the kit, hits get the shakers' full stroke, and gear shifts land as a real thud. It stops Spotter calls from shaking the seat, stops iRacing paved runoff rumbling like grass, and lets the FFB Lab take a wheel back in place after a brief loss of control (AI Coach v0.272). Includes 2.26.248. Saved haptics profiles are unchanged unless the driver takes the new feel. Supervised testing only; shaker feel and FFB recovery still need rig checks.

Beta [2.26.248](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.248) switches off Belt Tensioners and Wind Sim while they are being finished and tested, and lets Blip coach against verified trackside boards, kerbs and landmarks with the car's measured brake, turn-in and throttle points (AI Coach v0.272). Includes 2.26.247. Supervised testing only; plan changes have not yet been run against a real card charge, trackside references cover only verified corners, and live headset/shaker, simulator, streaming-provider and installed-upgrade checks remain pending.

Beta [2.26.247](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.247) shows each plan's AI Coach talk time and chat allowance, lets subscribers change plans in the app with the exact price shown first, fixes the plan cards and the signed-out trial label, removes the Home checklist, and brings Blip lap reads, Spotter traffic and recovery fixes, Endurance overlays, pedal upgrade recovery, belt tensioner tuning and a Visual C++ runtime fix to the installer (AI Coach v0.271). Includes 2.26.245. Supervised testing only; plan changes have not yet been run against a real card charge, and live headset/shaker, simulator, streaming-provider and installed-upgrade checks remain pending. Some screens still show English when Spanish is selected.

Beta [2.26.245](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.245) grounds Blip advice in measured results, adds supported slide explanations, protects voice routing from configured shaker outputs, expands stock Spotter reactions, and improves Setup Shop version tracking, Endurance sharing and overlay tests, streaming chat, floating track maps and wheel previews (AI Coach v0.270). Includes 2.26.244. Supervised testing only; live headset/shaker, simulator, streaming-provider and installed-upgrade checks remain pending. Every changed setup still needs its own garage and driving checks. Hosted feature activation is separate; creator conversion rewards are not activated by this installer. Some screens still show English when Spanish is selected.

Beta [2.26.244](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.244) improves Blip race information, fast-repair receipts, interrupted answers and corner references; restores lap-time Spotter reports; adds guided TrackPro Studio setup; and improves Setup Shop receipts and completed-season Race Pass results (AI Coach v0.269). Includes 2.26.243. Supervised testing only; live headset, simulator/provider and installed-upgrade checks remain pending. The Fuji correction passes recorded-session checks; three-game live acceptance remains separate. Pit-rejoin estimates remain uncalibrated, and hosted Setup Shop/streaming activation is separate. Some screens still show English when Spanish is selected.

Beta [2.26.243](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.243) combines Setup Shop starting files, TrackPro Studio controls for OBS/Streamlabs, Works Team and optional combined chat, the iRacing Endurance hub, Wheel Studio improvements, Blip control readiness and audio recovery, and Brake Approach updates (AI Coach v0.268). Includes 2.26.242. Supervised testing only; live simulator, headset, streaming-provider and installed-upgrade checks remain pending. Hosted feature activation is separate, and the known Fuji replay issue remains open.

Beta [2.26.242](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.242) removes redundant confirmations for direct Blip requests, fixes game chat and visor control routing, discovers simulator controls and supports observed parked setup for missing keyboard mappings (AI Coach v0.267). It also improves Spotter audio output recovery. Includes 2.26.240 and the unpublished 2.26.241 work. Controls unassigned everywhere still require parked setup; live driving, hardware and installed-app acceptance remain pending.

Beta [2.26.240](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.240) fixes recording audio interruptions, dashboard startup, expired-login session history and delayed Settings navigation. It also corrects FFB wheel setup and adds an optional FFB Lab toggle for the invited test account. Includes 2.26.239; AI Coach v0.265 is unchanged. Supervised testing only; physical wheel compatibility, LED output and installed-app acceptance remain pending.

Beta [2.26.239](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.239) combines the latest Blip guided-lap and reference work, per-output haptics tuning, Govee recovery and placement, brake guidance, shared maps, dial controls and community chat (AI Coach v0.265). Includes 2.26.238. Supervised testing only; live listening, driving and physical hardware acceptance remain pending.

Beta [2.26.238](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.238) shows coaching data delivery status and improves the completeness of Blip's advice and practice-comparison records (AI Coach v0.264). Everything in 2.26.236 is included. Supervised testing only; live listening and driving-improvement acceptance remain pending.

Beta [2.26.236](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.236) tracks Blip's coaching playback and comparable later corner results, and fixes enrollment in the practice comparison (AI Coach v0.263). Everything in 2.26.235 is included. Playback starts and later gains are measured separately; they do not prove the driver heard a full call or that coaching caused an improvement. Supervised testing only.

Beta [2.26.235](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.235) preserves community voice word beginnings and pauses while filtering rumble, improves seat haptics and output sharing, and fixes Govee ambient lighting and wheel connection diagnostics. Everything in 2.26.234 is included. Physical rig acceptance is still pending; supervised testing only.

Beta [2.26.234](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.234) lights recognised dashboards and DDUs automatically (the SIMDID DV480 and other VoCore dashes, Ascher, GRID, PSE and more), and waits for any other dash program to close instead of fighting it. Everything in 2.26.233 is included.

Beta [2.26.233](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.233) lights DDU and DIY LED boards (Find LED device in Wheel Studio), fixes 5-14 second window freezes on some PCs, makes the 4th-monitor dash cover the taskbar, and draws dash track maps correctly. Everything in 2.26.232 is included.

Beta [2.26.232](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.232) puts flags and the spotter on every wheel's side lights (green, yellow, blue, white, black, checkered, red, car left and right), brings flags from F1, rFactor 2 and Le Mans Ultimate to the wheel, lights MOZA rims, fixes Simagic and Fanatec lights, matches 120+ wheels to their makers' setups, and ties every button binding to its device (AI Coach v0.262). Everything in 2.26.231 is included.

Beta [2.26.231](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.231) makes every wheel LED combo work (2.26.230 shipped an older engine that refused them), sharpens wheel-screen text, adds new dashes (Endurance Pro, Oval Pro, Stage Pro, Navigator Pro, Pocket), a 4th-monitor dash, see-through and a touch Control Panel (AI Coach v0.261). Everything in 2.26.230 is included.

Beta [2.26.230](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.230) puts the brain's coaching model on your PC: in practice, Blip calls the corner that cost the most, the phase and the fix when the brain and the measurement agree (AI Coach v0.260). Everything in 2.26.229 is included.

Beta [2.26.229](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.229) makes wheel LEDs follow the game with one click, lights every wheel the way its maker set it up (rev, side and button lights from each maker's own setup, per-car rev lights, lock-up lights), reworks the wheel dash, and Blip remembers you across sessions and PCs (AI Coach v0.259). Everything in 2.26.228 is included.

Beta [2.26.228](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.228) plays the coach's focus calls again without the live coach voice, answers "where am I losing time" against the fast drivers in your car from lap 1 (AI Coach v0.258), and has the Spotter say what happened instead of incident points. Everything in 2.26.227 is included.

Beta [2.26.227](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.227) adds the fair test: in practice the coach sometimes waits, at random, before taking on a new corner, so we can measure how much its calls really help (AI Coach v0.257). Everything in 2.26.226 is included.

Beta [2.26.226](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.226) uploads every driver's corner times on every sim, saves untimed laps instead of dropping them, and makes the coach's calls fairer: no trail-brake call where it slowed drivers, and calls graded against the same fault with no call (AI Coach v0.256). Everything in 2.26.225 is included.

Beta [2.26.225](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.225) makes Blip's "He already found time in your laps" and Corner mastery judge each lap by its saved lap time; on iRacing, versions before 2.26.186 stored the previous lap's time on every corner (AI Coach v0.255, unchanged). Everything in 2.26.224 is included.

Beta [2.26.224](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.224) makes Blip number laps the way the sim does on Assetto Corsa, ACC, rFactor 2 and Le Mans Ultimate (it ran one lap behind the HUD), makes "compare my laps" read the laps you asked for, and stops AC saving lap 1 as a copy of lap 2 (AI Coach v0.255). Everything in 2.26.223 is included.

Beta [2.26.223](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.223) makes onboard recording film the centre screen on triple-screen rigs (it was picking a side screen) and gives Blip corner targets from the brain trained nightly on the server (AI Coach v0.254). Everything in 2.26.222 is included.

Beta [2.26.222](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.222) makes the coach's reference follow the database live: a quicker clean lap another driver banks during your session counts within about twenty seconds and the coach says so once (AI Coach v0.253). Spotter Market voices now say their own turn numbers. Everything in 2.26.221 is included.

Beta [2.26.221](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.221) speaks brake points as trackside markers wherever a verified marker is in reach ("brake right at the 100 board", "between the 100 and 50 boards"), replacing the meters in the pre-corner call, the guided lap and Blip's corner answers (AI Coach v0.252). Everything in 2.26.220 is included.

Beta [2.26.220](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.220) makes the coach's reference the fastest clean lap any other driver set for your car and track (AI Coach v0.251), and teaches the Support agent the Spotter and Blip: it checks whether your sim is connected, whether the Spotter is switched on and where the radio is playing, and can turn the Spotter on for you. Everything in 2.26.219 is included.

Beta [2.26.219](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.219) lets Blip change your in-car dials (TC, ABS, bias, bars, maps) through iRacing's F8 box with the change proven in telemetry, read a rival's lap every lap, fixes the start/finish gap read, keeps the spotter quiet in lone qualifying, and cuts headset screeches out of voice chat on both ends (AI Coach v0.250). Everything in 2.26.218 is included.

Beta [2.26.218](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.218) makes the Force Feedback page drive the wheel in Assetto Corsa: AC's gain is held at 5% (not 0, which blanked the steering force) and divided back out, and the page never judges one sim by another sim's last frame. Everything in 2.26.217 is included.

Beta [2.26.217](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.217) finds a throttle whose sensor lead was moved to another port during calibration, as the brake and clutch already were. Everything in 2.26.216 is included.

Earlier beta builds, all included in 2.26.216 (their notes describe each build as it was tested):

Beta [2.26.215](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.215) keeps the Lebois SRT80 a beta-channel option until it has run on a rig, no longer takes a Thanos or SRT80 controller at launch (press Enable), and is the candidate for the next stable release (AI Coach v0.249). Everything in 2.26.214 is included.

Beta [2.26.214](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.214) has the AI Coach call the corner you are working on live in practice ("Brake now.", "Turn in.", "Keep turning.", "Unwind.", "Accelerate."), speak in short instant clips, and treat suggestions per lap as a real count; it also supports Lebois SRT80 control boxes on firmware 2.1 (AI Coach v0.249). Everything in 2.26.213 is included.

Beta [2.26.213](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.213) makes TrackPro stop and latch motion the moment the rig's physical E-stop is pressed, read from the Sim Coaches Control Center display (its updated firmware required) (AI Coach v0.248). Everything in 2.26.212 is included; supervised testing only.

Beta [2.26.212](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.212) adds Race mode for the rig's corner LEDs: every flag and the start lights, pit lane and limiter, cars alongside, ABS and TC, a rev bar on the fronts and brake and throttle on the rears, each in its own colour with a Test button per cue; the Native 360 Hz diagnostics tile no longer fails healthy rigs (AI Coach v0.248). Everything in 2.26.211 is included; supervised testing only.

Beta [2.26.211](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.211) makes overlays fit at any display scale with a 50-200% size slider and free placement, makes the FFB overlay's buttons work, fixes the haptics Lo/Hi frequency sliders, and has the AI Coach describe positions from the apex instead of lap distances (AI Coach v0.248). Everything in 2.26.210 is included; supervised testing only.

Beta [2.26.210](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.210) makes the rig move as one rigid body with no diagonal frame twist, adds a live motion monitor on the Motion page, and makes corner LEDs work with Pro Micro boards (AI Coach v0.247). Everything in 2.26.209 is included; supervised testing only.

Beta [2.26.209](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.209) makes the rig lean into banking instead of cancelling it, drops the seat over crests and lifts it in compressions, maps each track's hills and banking and plays them a moment early, adds a Track feel card on the Motion page, and lets you ride along your last lap on the rig (AI Coach v0.247). Everything in 2.26.208 is included; supervised testing only.

Beta [2.26.208](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.208) makes kerb rumble hit hard on the actuators on the side that is on the kerb, gives elevation, suspension and haptics their own share of the stroke, and learns each track's banking and hills so Daytona's banking and big climbs use the travel (AI Coach v0.247). Everything in 2.26.207 is included; supervised testing only.

Beta [2.26.207](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.207) gives kerbs a hard thunk on the side and tyre that hit them, lets actuator haptics play at full strength again, puts track elevation ahead of suspension in the Omega motion tune, drives the rig's corner LEDs itself, lifts shaker kerbs above the engine, and lets Blip run without a microphone (AI Coach v0.247). Everything in 2.26.206 is included; supervised testing only.

Beta [2.26.206](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.206) runs motion tests started from the paired phone at 25% speed (enforced by the PC) and adds the full travel check to the phone, which runs only from Stopped and never leaves motion enabled. Everything in 2.26.205 is included; supervised testing only.

Beta [2.26.205](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.205) starts motion cues up to 3x sooner on every profile (the seat moves about 20 ms after the car's G on a brake stab), adds the Lebois SRT80 control box, an in-app handbrake firmware updater and phone control of every motion setting, lets new PCs drive first and sign up after, and brings AI Coach v0.246: doubled allowances, out-of-talk-time lines in every coach language, and guided "Brake now." calls on time under load. Everything in 2.26.204 is included; supervised testing only.

Beta [2.26.204](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.204) rebuilds Force Feedback around a simple page with an automatic setup check (rotation, force direction, clipping) and car-first effects: shifts are a small knock that cannot pull the wheel, ABS pumps the steering weight, and effects grey out in games that cannot drive them. Haptics outputs recover on their own and name who holds them, and Community gains a support channel. Everything in 2.26.203 is included; supervised testing only.

Beta [2.26.203](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.203) stops TrackPro from disturbing other motion software's VR motion compensation while TrackPro motion is off, lets custom games drive the motion platform (Generic Motion Telemetry v1 over UDP), and moves corner calls to iRacing's official turn numbers with Blip's ElevenLabs voices on Eleven v4 (AI Coach v0.245). Custom Spotter voices now come as three distinct takes. Everything in 2.26.202 is included; supervised testing only.

Beta [2.26.202](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.202) keeps League Night results from going missing: result saves retry until they land (even across a restart), a grid-time session no longer records your grid slot, and the server now places drivers whose result never arrived. Google profile pictures load again, and FFB Lab brings lost force back in under a second. Everything in 2.26.201 is included; supervised testing only.

Beta [2.26.201](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.201) makes custom Spotter voices usable in about 7 minutes, builds corner names only for the tracks you race with them on, and updates installed voices by themselves. It also fixes the Blip page flashing a sign-up screen and Navarra's corner numbers (AI Coach v0.244), and adds FFB Lab strength to 60 Nm with an end-stop guard. Everything in 2.26.200 is included; supervised testing only.

Beta [2.26.200](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.200) puts every Spotter Market voice in the Spotter voice menu for everyone and lets Pro 5× and Pro 20× members give Blip any of them (AI Coach v0.243). The Spotter's and Blip's radio clicks now follow their volume, and custom voices follow their description more closely. Everything in 2.26.199 is included; supervised testing only.

Beta [2.26.199](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.199) lets Blip tune your motion rig by voice on track, clear your own black flag in iRacing, and act as your endurance and oval strategist (AI Coach v0.242). The spotter now names the car to follow under caution, and a new motion Anticipation setting (off by default) starts cues from your steering, brake and throttle. Everything in 2.26.198 is included; motion needs rig acceptance; supervised testing only.

Beta [2.26.190](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.190) fixes AI Coach silences after actions and exact spoken volume levels.

Beta [2.26.189](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.189) adds AI Coach evidence, map, fuel and briefing improvements, and the in-game FFB overlay. It includes the 2.26.188 motion changes, which remain on validation hold.

Validation candidate [2.26.188](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.188) contains further motion persistence and controller-protocol corrections. **Supervised testing only; not approved for customer delivery.**

Beta [2.26.187](https://github.com/SimCoaches/TrackProV2/releases/tag/v2.26.187) is on **validation hold - do not use for customer delivery**. Reliability fixes and physical Thanos4U acceptance are pending.

### What's New in 2.26.266

- Blip, your AI Coach: coaches against a lap you choose, calls every corner that lost time, brake-board coaching, corner targets from the nightly TrackPro Brain, and six voices.
- Motion: a big bump or crash no longer turns motion off for the session, motion follows the game (truck games and racing games each get the right profile), smoother Omega defaults.
- Force feedback no longer goes silent after iRacing loads a session.
- Haptics: Optimized and Refined mixes (opt-in), Road Texture felt on iRacing, 100% means full stroke, a Background dip slider on priority effects.
- Phone and tablet dash on any device on the same Wi-Fi, no app needed; faster, lighter ambient lighting with automatic setup; flags and spotter on wheel side lights.
- See the [changelog](CHANGELOG.md) for all changes since 2.26.216.

### What's New in 2.26.216

- Blip, your AI Coach: calls the corner you are working on live in practice ("Brake now.", "Turn in.", "Keep turning.", "Unwind.", "Accelerate."), speaks in short instant clips, coaches as many corners per lap as you set, stays quiet in qualifying and is your race engineer in a race.
- Motion: cues start sooner, kerbs and elevation felt separately, a Motion setup page with a response test, the rig's physical E-stop read by TrackPro, and a Thanos controller left alone until you press Enable (Stop releases it for other software).
- Force Feedback page rebuilt, haptics mixer and feel, corner LEDs with a Race mode, Spotter page and voice market, handbrake firmware updater, phone companion.
- Lebois SRT80 support is on the beta channel only until it has been run on a rig.
- See the [changelog](CHANGELOG.md) for all changes since 2.26.181.

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
