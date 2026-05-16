# TITAN-7

A single-file ASMR mech walking simulator. Recon a procedurally generated, infinite Appalachian wilderness with your golden retriever, your remote crew engineer, a recon drone, and three friendly allied mechs. The sky changes. The weather rolls through. The news wire keeps you company. There are unfound hatches in every direction, hidden network nodes scrawled on scavenged hardware, and a private bulletin board no one will admit exists.

```
       ╱│ ╲                            ╱ │╲
      ╱ │  ╲      ┌──────────┐        ╱  │ ╲
     │  ▓▓  │     │  TITAN-7 │       │  ▓▓  │
     │  ██  ├─────┤   ◢ ◣    ├───────┤  ██  │
     │      │     │   ███    │       │      │
      ╲    ╱      └────┬─────┘        ╲    ╱
       ╲  ╱            │                ╲  ╱
        ╲╱        ┌────┴────┐            ╲╱
                  │ █  ◉  █ │
                  │  ┌─┴─┐  │
                 ╱└──┘   └──┘╲
                ╱    │   │    ╲
               ╱     │   │     ╲
              ▔▔▔▔▔▔▔     ▔▔▔▔▔▔▔
```

## What it is

TITAN-7 is a slow, contemplative first-person mech sim built as one HTML file. The pitch is "engineering ASMR meets walking sim." There is technically a defensive combat layer, but the world is quiet by design and most of the play loop is about looking at things, reading them, and walking somewhere else.

The setting is reclaimed Appalachian territory after some unspecified collapse, with the visual and naming language of Fallout 76 (vaults, hatches, the numbers 4-8-15-16-23-42) crossed with LOST (DHARMA-style stations, anomalous monoliths, bamboo where it should not be). Mountains in the distance, smoke pillars on the horizon, weather that drifts in over the river basin.

You walk. You scan. You read the readouts. You note the small chime at the henge. You hear that Charleston won by six lengths. Coral leans into the pedals.

When the road gets long, you find yourself sitting somewhere quiet and typing a name onto your map. Or jacking into a network that only knows you by a handle. Or reading a poem somebody else taped inside a kitchen cabinet, eighty years ago.

## Features

### World

* Procedurally generated, infinite in every direction. Chunks load and dispose around the player on a configurable active window.
* Seven biomes (pine forest, birch grove, dead marsh, open meadow, burned forest, rocky highland, bamboo grove), each with distinct flora densities, ground patches, water disks, ash sediment, or boulder fields.
* Each chunk hosts roughly 32 manmade props and 8 natural props on top of the standard tree, rock, grass, and bamboo distribution. Across loaded chunks that totals around 800 manmade items and 200 natural ones at any given time.
* Twelve POI types with evocative procedural names. DHARMA OUTPOST 16, THE PEARL STATION, ANOMALY 4-8-15, MORGANTOWN REST STOP, COPPER FALLS LIGHTHOUSE, etc.
* Five drifting passphrase NPCs scattered through the world at specific POI types. A beekeeper, a tower keeper, an old trader, a lighthouse keeper, and a figure at an overlook who will not give a name. Each has a small conversation tree. Each recognizes the GREENROOM passphrase and pays out a unique reward to anyone who knows it.

### Day, night, and weather

* Eight-minute day/night cycle. Five phases (dawn, day, dusk, evening, night) with their own lighting palette and fog density.
* Sun arcs east-to-west during daylight. Sky and ambient lights interpolate between phases.
* Nine weather states with particle precipitation (clear, golden hour, overcast, heavy mist, light rain, passing storm, light snow, dusty haze, dusk). They transition probabilistically every 90 seconds to 5 minutes.
* Night Vision Goggles auto-engage at night and disengage at dawn. Manual N-key toggle for daytime use or to opt out of the auto behavior.

### Crew and companions

* Coral, golden retriever, riding in the cockpit. Rendered in profile-view 2D canvas with five animated states (settled, alert, excited, worried, snoozing). She blinks, her tail wags, her ears flick, and she narrates ambient feelings through her status panel. She reacts to discoveries, hits, and nearby allied mechs.
* Kailey, the remote crew engineer. Speaks on comms in pink-magenta text. Periodic status checks, personal observations, and event reactions. She has a separate set of observation lines that surface only when you have a registered GREENROOM handle, hinting that she is quietly watching out for you.
* Three procedurally named allied mechs (TITAN-3 // BRIGGS, COL-9 // KAYA, etc.) walking the same wilderness. Visible as cyclops-eyed bipedal walkers in the distance. Broadcasting ambient chatter on Channel 47. Press H to hail the nearest one within 200m.
* A recon drone, deployable with Q. Octahedron body with four rotors. Orbits at 50m radius and 55m altitude. Auto-discovers POIs within 80m. Battery drains at 1.5%/s, charges 3%/s while docked.

### Comms and information layers

* Channel 47 comms log on the lower-left. Mech status, hail responses, weather wire, news wire, Kailey chatter.
* News wire drops a randomized story every two to five minutes from a pool of stories covering sports, pop culture, politics, community, and local oddities.
* Tunable cockpit radio (88.0 to 108.0 MHz). Eleven stations and a roving pirate broadcaster. Weather Service, News Wire, Caravan Band, Distress, Station 47 (numbers), Dharma Relay, Night Bird (music), Pre-War Archive, Ranger Net, Open Channel, and the in-cockpit intercom on Channel 47. Signal clarity falls off with distance from the channel. Scan and snap-to-channel buttons. Holotape playback at a dedicated frequency.
* Field logbook (L key). Timestamped session log with categorized entries (discovery, maintenance, combat, comms, travel, system). Scrollable. Newest entries at the top.
* Field journal (J key). Auto-composed phase-transition summaries of where you walked, what you scanned, who you hailed, and what came of it. Reads like the pilot's diary written at the end of each watch. Now also surfaces the pilot's hand-written field notes (see below) at the top of the same panel.
* Codex (K key). Two tabs:
    * **ARCHIVES**: lore fragments recovered from POIs and scans. Multi-part stories that piece together over time. DHARMA logs, pilot black-box recordings, the Numbers, tableau observations, pirate radio transcripts.
    * **RECOVERED**: human culture preserved by the wasteland. Poems, sheet music, recipes, postcards, letters, a child's drawing of a lighthouse. Public-domain Frost, Dickinson, Whitman, "Shenandoah," "Amazing Grace," Sir Patrick Spens. Found as small `PRESERVED WRITING` items in glove compartments, on church pews, taped inside kitchen cabinets, pressed in paperbacks. Rendered in a serif typeface, distinct from the amber CRT monospace of the lore archives.

### Diagnostics and repair

* Diagnostics panel (T key) with ten subsystems: reactor core, leg hydraulics (left and right), torso gimbal, cockpit enviro, neural link, sensor array, coolant loop, weapon systems, exterior plating.
* Live engineering readouts per subsystem (output kW, flux Sv/h, gyro drift, O2 percent, neural latency, S/N dB, coolant delta-T, etc.) that wobble slightly each frame.
* Damage taken in combat distributes to random subsystems weighted by mass.
* Three mini-game types assigned by subsystem:
    * Pressure Stabilization (reactor, coolant, plating). Tap when the needle is in the green band, three locks required.
    * Wave Sync (legs, gimbal, sensor). Drag horizontally to phase-align two sine waves, hold sync for two seconds.
    * Pattern Recall (weapons, cockpit, neural). Watch a 3-to-6-step flash sequence and repeat it on a 4-cell grid.
* Two failed attempts unlocks a "Hand Off To Kailey" option. She solves the repair remotely after a short pause.

### Map, scan, navigation

* Recon map (M key). Full-screen overlay with grid, all POIs (green squares for surveyed, amber diamonds pulsing for unclassified), allied mechs as labeled blue dots, drone position with scan radius, player triangle rotating to current yaw.
* Left-click sets a waypoint at world coordinates. The mech walks itself there. Right-click drops a named place marker. Shift plus right-click clears your route. Scroll wheel zooms 0.2x to 4x.
* Click-and-scan mode. Aim the cursor reticle anywhere and left-click to scan whatever it is over. Returns class, distance, material, bearing, and a Kailey commentary line. Works on POIs, allied mechs, sentinels, trees, rocks, debris, manmade props.

### Personal cartography (Player Leaves Marks)

* **Place Names.** Right-click anywhere on the map to drop a named marker. Type up to 48 characters. The Lookout Where I Saw The Geese. Where The Music Was. Bennett's Ridge. The Bend Where Coral Growled. The names persist across sessions as small amber diamonds with their labels, slowly turning the map into a personal atlas.
* **Field Notes.** Press B anywhere in the cockpit to write a freeform note pinned to your current coordinates. Up to 280 characters. CTRL+ENTER saves. Notes render as small amber circles on the map and accumulate in a "Field Notes" section at the top of the journal, listed most recent first. Each note records the date, time, and exact coordinates of where you were when you wrote it. Click any field note dot on the map to read its contents later.

### The GREENROOM (hidden BBS network)

A rumored, mostly-secret community bulletin board the player can discover and join. Found by stumbling on a node address scrawled on a salvaged item, told by someone in a graffiti tableau, or whispered by an NPC at an overlook. Once you have a node address, the local terminal can dial it.

* **Connection ritual.** DTMF tones, modem handshake noises, carrier-lock chime, ASCII splash header, slow typewriter rendering. The session lives on a phosphor-green CRT overlay with scanline texture and a soft vignette, distinct from the amber HUD of the rest of the sim.
* **Account.** Register a handle on first connect (A-Z, 0-9, underscore, 4-12 characters). Some handles are reserved as memorials. The handle persists, can be changed once at minor cost.
* **Five message boards.** GENERAL, TECH/MODS, ENCOUNTERS, LORE, TRADE. Together they host roughly 50 thread posts written in the voice of ten distinct regulars. NIGHTOWL the sysop, PROXY_M the paranoid signal scout, CABLEHEAD the file librarian, WIRE_SAINT the radio mystic, OLD_LION the memorial keeper, APRIL the ghost who almost never posts, null_pointer who only posts timestamps, HARLOW the southern radio operator, and a handful of others.
* **Replies and rapport.** Many threads offer the player tonal-choice reply options. Each reply silently nudges your rapport with the regulars who care about the topic. Rapport is visible in the USERS list color-coded. NPC follow-up replies may appear in threads where you've responded.
* **Private mail.** Trigger-based PMs arrive based on player behavior. A welcome message from NIGHTOWL after first login. A thanks from WIRE_SAINT after replying to certain posts. An audit warning from CABLEHEAD if you install a corrupted patch. And others.
* **Firmware library.** Eight downloadable mech patches available through the GREENROOM FILES board. Patches install via an XMODEM-style progress bar with KB/s and ETA readouts, then take effect on real mech systems: radar range, coolant dissipation, chaingun heat, gimbal drift, drone speed and battery, footstep audio, and a NEURAL FIREWALL that actually defends against the trace event (see below). Each patch has a 3% chance to be trojan-corrupted on install, inverting its effect and prompting community responses on the TECH/MODS board.
* **Layered access.** Four threads on LORE and ENCOUNTERS are encrypted at Layer 2 and only readable if the player has unlocked a matching decrypt fragment in the codex. The thread body shows `[CONTENT ENCRYPTED]` until the key is in hand.
* **The Vault.** A third tier accessible only after solving the hardest cipher (`decrypt_vault_key`). The Vault is rendered in amber accent on the green CRT and contains a small archive left by the network's founder: a charter from 2043, a memorial archive of dead regulars, and a long farewell letter signed `// b`. Reading the letter is meant to be the emotional center of the network.
* **Brain-spike tracing.** Sessions on GREENROOM are not safe forever. At about 25 minutes of continuous connection, the network's adversaries detect your carrier. A LINK ANOMALY warning appears at the top of the body, the carrier-lock indicator turns red, NIGHTOWL drops a sysop alert in the comm log, and three 880Hz alarm pulses play. The player has 90 seconds to disconnect. Failing that, a brain-spike fires: the entire overlay does a 2.5-second jitter animation with hue-rotated distortion, a harsh distorted audio burst plays, the neural subsystem takes 25 damage, and the connection is forcibly closed. The NEURAL FIREWALL patch buys you an earlier warning, more grace time, and reduces damage on impact.
* **Discovery items.** Three rare scavengeable items contain hidden node addresses. A tarnished modem cable, a muddied address paper, a green phosphor fuse. First-pickup of any of them adds a new node to your routing table. The `connect` and `nodes` terminal commands let you dial discovered nodes.
* **Mute zones.** Henge and anomaly POIs emit a carrier-suppression field. The closer you are, the more degraded your lock becomes. Inside the inner zone, GREENROOM refuses to connect. Walking into one while connected force-disconnects you with a sysop comm: "carrier lost. you walked into something that does not want you here."

### Local terminal

* Press backtick (`` ` ``) to summon a small CRT-style command-line terminal in the cockpit. Commands include `connect <address>` to dial a GREENROOM node, `nodes` to list discovered addresses, `firmware` to show installed patches and their modifiers, and `trace <minutes>` to debug the brain-spike timer.

### Settings and accessibility

* Settings panel (O key in-game, or `[settings]` button on the start screen). Pauses the world while open. Changes save automatically and apply immediately.
* Audio: master volume slider, ambient sounds toggle (wind, rain, reactor hum), muffled footsteps toggle. The ambient toggle is also surfaced as a small `♪ AMBIENT ON / OFF` badge inline with the WEATHER FORECAST header on the starboard panel so it's reachable without opening the settings panel.
* Graphics: render distance (LOW / MED / HIGH, mapping to chunk-load radius 1, 2, or 3), shadows toggle, field-of-view slider (60 to 95 degrees).
* Accessibility: reduced-motion toggle (disables jitter and glitch effects throughout the sim and the GREENROOM), HUD scale (NORMAL or LARGE for higher readability).
* Themed CSS scrollbars throughout the sim. Amber HUD style by default. Phosphor green inside the GREENROOM.

### Start-screen options

* Pilot name and callsign entry on launch.
* Tappable `[settings]` button.
* Tappable `[reset all saved data]` button with a confirmation modal. Wipes every persistent key the sim writes (pilot ID, progression, GREENROOM state, firmware, NPC assignments, place names, field notes, settings, etc.) and reloads the page from a clean slate.

### Controls

* Cursor reticle replaces the system pointer during play. The view does not rotate with the mouse.
* WASD to strafe forward, back, left, right.
* Left and right arrow keys turn yaw.
* Up and down arrow keys pitch the view.
* Mouse aims the reticle. Left-click scans, right-click holds for chaingun fire. F launches a defensive missile.
* Shift to boost, Space for jump jets, Z to kneel or stand.
* M (map), T (diagnostics), L (logbook), J (journal), K (codex), Q (drone), H (hail nearest mech), N (vision cycle), E (talk to nearby person), B (write field note at current spot), O (settings), backtick (terminal), Escape (pause, or close any open menu).
* Mechanical on-screen console at the bottom-right has clickable buttons for every command, styled as a rugged military panel with rivets. Useful as a mnemonic and clickable when paused.

## Running it

Open `mech_sim.html` in any modern desktop browser. That is the entire installation step.

There are no build tools, no package manifests, no server requirements. Three.js (r128) loads from a CDN at runtime. The file is a single self-contained HTML document of roughly 1 MB. Save state is held in browser localStorage under a handful of `titan7_` and related keys.

If you want to host it yourself, drop the file behind any static webserver. Tested on Chrome, Firefox, and Safari.

## Architecture

Everything lives in `mech_sim.html`. The file is organized roughly in this order:

1. Inline CSS (lighting palette, HUD, panels, overlays, mini-games, weather, NVG, control console, GREENROOM CRT, settings overlay, modals, themed scrollbars).
2. Inline HTML (HUD frames, badges, overlays, start screen, game-over, pause, GREENROOM full-screen overlay, settings overlay, NPC dialog, place-name and field-note modals, reset confirmation).
3. One inline `<script>` containing:
    * Scene setup, lighting, fog, sky, mountains, smoke pillar.
    * Player state and physics.
    * Procedural world (mulberry32 PRNG, biome assignment, chunk load/unload, POI builders, prop builders).
    * Coral, Kailey, allied mechs, drone, diagnostics, mini-games, scan, logbook, comms, news wire, journal, codex.
    * Day/night cycle and NVG overlay.
    * Tunable radio: 11 stations plus pirate broadcasts plus holotape playback, with signal clarity falloff.
    * GREENROOM data tables (regulars, boards, posts, replies, reply options, encrypted threads, vault content, trojan templates), state object, save/load, and full UI rendering pipeline.
    * Firmware system: 8 patches, install flow, recompute of mod multipliers, hooks into game systems (radar, coolant, chaingun heat, gimbal, drone, footsteps, neural firewall).
    * Passphrase NPC system: definitions, chunk-load assignment, mesh building, interaction prompt, dialog overlay, reward application.
    * Personal cartography: place names module, field notes module, modal handlers, map rendering, journal section.
    * Found human culture: codex tab system, recovered entries, item drop hook.
    * Settings: defaults, load/save, apply pipeline, UI sync.
    * Input (keyboard, mouse, on-screen console).
    * Main loop.

The file is intentionally one document. Editing happens in place. Loading is one HTTP request. State resets cleanly on restart.

### Rendering

Three.js r128, MeshStandardMaterial throughout, one directional light (the sun), one ambient light, FogExp2. No post-processing pipeline. NVG and weather effects are CSS overlays composited over the canvas. The cursor reticle is an inline SVG element following the mouse. The GREENROOM overlay is a full-screen CSS surface with its own scanline and vignette, layered on top of the 3D canvas when connected.

### Procedural generation

* `mulberry32` PRNG seeded by chunk coordinates plus a salt for deterministic regeneration.
* Two-octave coarse noise picks biomes so they form blobs rather than checkerboards.
* POI metadata persists in a Map keyed by `chunk#index`, so reloading a chunk recovers the same names and types. Tree, rock, and prop placement is regenerated from the chunk seed each load.
* Obstacles inside chunk bounds are removed on unload so collision stays consistent with what is visible.
* Passphrase NPCs assign themselves to the first matching POI type the player discovers and stay there forever (persisted to localStorage). Different pilots get different NPC placements, but the same pilot always finds them in the same spots.

### Persistence

Local browser storage only. The sim is offline-first. Keys include:

* `titan7_pilot` (name and callsign)
* `titan7_progression` (run state)
* `titan7_settings` (audio, graphics, accessibility preferences)
* `titan7_ambient_muted`, `footstepMuffled`, `cpCollapsed` (legacy single-purpose keys, kept in sync with the settings object)
* `greenroom` (handle, posts read, replies sent, rapport, mail, verified status, vault entered, dynamic posts, discovered nodes)
* `firmware` (installed patches and library "seen" markers)
* `titan7_npcs` (passphrase NPC placement, who you've spoken to, who has paid out a reward)
* `titan7_placeNames` (named map markers)
* `titan7_fieldNotes` (pilot's freeform notes)

The start-screen reset button erases all of these and reloads the page.

## Design notes

The goal was to make something quiet to walk around in. Engineering ASMR is the operative phrase. Lots of readouts to look at, lots of numbers that wobble in pleasing ways, a friendly voice on the radio, a dog at your feet, a sky that changes slowly. Combat exists but is rare and easy. The sentinels stay passive unless you bother them. The mech regenerates HP. Damage routes to subsystems that you repair through small relaxed mini-games.

Naming was lifted unapologetically from LOST and Fallout 76 because those two universes already share an Appalachian-adjacent, post-collapse, anomalous-numbers vibe and combining them produces names that feel right with no further work.

The control scheme is deliberately tabletop. No FPS mouselook, no pointer lock, no twitch response. You turn with the arrow keys. You aim with the cursor. You can sit back and let the mech walk to a waypoint while you watch the weather change.

Later additions push further in the same direction. The GREENROOM is a private bulletin board to read at your own pace, with a slow community of regulars whose tone you can read after a while. Place names and field notes let the world become a thing you've inhabited, not just visited. The Recovered codex tab makes the wasteland a place that remembers what people wrote, what people kept, what people taped inside cabinets. The passphrase NPCs reward attentiveness to the lore (anyone who has read the GREENROOM ABOUT page or the founder's farewell knows the words). The settings panel lets the sim adapt to whatever screen and ears you've got. All of it is meant to support sitting with this sim for an evening and feeling like you stopped somewhere.

## Influences

* Fallout 76 (Appalachian setting, vault language, retro-tech reclamation aesthetic)
* LOST (DHARMA stations, the numbers, the chimes, the hatches, the bamboo)
* Death Stranding (the walking, the radio chatter, the quiet middle distance)
* Hardspace: Shipbreaker (technical readouts, voice-only crew, repair as ritual)
* Outer Wilds (gentle exploration, small voice notes, weather)
* Truckers' CB radio (Channel 47, the news wire, the bored regional comms)
* Early BBSes and Fidonet (GREENROOM's whole tone, the regulars, the sysop, the dial-up ritual)
* American canon and Appalachian folk material (the Recovered codex tab: Frost, Dickinson, Whitman, "Shenandoah," "Amazing Grace," the anonymous ballads, the recipes nobody signed)

## File

* `mech_sim.html` (one file, around 1 MB, no dependencies bundled)

## License

GPL-3.0
