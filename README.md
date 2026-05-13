# TITAN-7

A single-file ASMR mech walking simulator. Recon a procedurally generated, infinite Appalachian wilderness with your golden retriever, your remote crew engineer, a recon drone, and three friendly allied mechs. The sky changes. The weather rolls through. The news wire keeps you company. There are unfound hatches in every direction.

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

## Features

### World

* Procedurally generated, infinite in every direction. Chunks load and dispose around the player on a 25-chunk active window.
* Seven biomes (pine forest, birch grove, dead marsh, open meadow, burned forest, rocky highland, bamboo grove), each with distinct flora densities, ground patches, water disks, ash sediment, or boulder fields.
* Each chunk hosts roughly 32 manmade props and 8 natural props on top of the standard tree, rock, grass, and bamboo distribution. Across loaded chunks that totals around 800 manmade items and 200 natural ones at any given time.
* Twelve POI types with evocative procedural names. DHARMA OUTPOST 16, THE PEARL STATION, ANOMALY 4-8-15, MORGANTOWN REST STOP, COPPER FALLS LIGHTHOUSE, etc.

### Day, night, and weather

* Eight-minute day/night cycle. Five phases (dawn, day, dusk, evening, night) with their own lighting palette and fog density.
* Sun arcs east-to-west during daylight. Sky and ambient lights interpolate between phases.
* Nine weather states with particle precipitation (clear, golden hour, overcast, heavy mist, light rain, passing storm, light snow, dusty haze, dusk). They transition probabilistically every 90 seconds to 5 minutes.
* Night Vision Goggles auto-engage at night and disengage at dawn. Manual N-key toggle for daytime use or to opt out of the auto behavior.

### Crew and companions

* Coral, golden retriever, riding in the cockpit. Rendered in profile-view 2D canvas with five animated states (settled, alert, excited, worried, snoozing). She blinks, her tail wags, her ears flick, and she narrates ambient feelings through her status panel. She reacts to discoveries, hits, and nearby allied mechs.
* Kailey, the remote crew engineer. Speaks on comms in pink-magenta text. Periodic status checks, personal observations, and event reactions. ("Pulled your coolant log. The loop is steady.")
* Three procedurally named allied mechs (TITAN-3 // BRIGGS, COL-9 // KAYA, etc.) walking the same wilderness. Visible as cyclops-eyed bipedal walkers in the distance. Broadcasting ambient chatter on Channel 47. Press H to hail the nearest one within 200m.
* A recon drone, deployable with Q. Octahedron body with four rotors. Orbits at 50m radius and 55m altitude. Auto-discovers POIs within 80m. Battery drains at 1.5%/s, charges 3%/s while docked.

### Comms and information layers

* Channel 47 comms log on the lower-left. Mech status, hail responses, weather wire, news wire, Kailey chatter.
* News wire drops a randomized story every two to five minutes from a pool of 24 lines covering sports, pop culture, politics, community, and local oddities.
* Field logbook (L key). Timestamped session log with categorized entries (discovery, maintenance, combat, comms, travel, system). Scrollable. Newest entries at the top.

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

* Recon map (M key). Full-screen overlay with 100m grid, all POIs (green squares for surveyed, amber diamonds pulsing for unclassified), allied mechs as labeled blue dots, drone position with scan radius, player triangle rotating to current yaw.
* Left-click sets a waypoint at world coordinates. The mech walks itself there. Right-click clears it. Scroll wheel zooms 0.2x to 4x.
* Click-and-scan mode. Aim the cursor reticle anywhere and left-click to scan whatever it is over. Returns class, distance, material, bearing, and a Kailey commentary line. Works on POIs, allied mechs, sentinels, trees, rocks, debris, manmade props.

### Controls

* Cursor reticle replaces the system pointer during play. The view does not rotate with the mouse.
* WASD to strafe forward, back, left, right.
* Left and right arrow keys turn yaw.
* Up and down arrow keys pitch the view.
* Mouse aims the reticle. Left-click scans, right-click holds for chaingun fire. F launches a defensive missile.
* Shift to boost, Space for jump jets.
* M (map), T (diagnostics), L (logbook), Q (drone), H (hail), N (NVG), Escape (pause, or close any open menu).
* Mechanical on-screen console at the bottom-right has clickable buttons for every command, styled as a rugged military panel with rivets. Useful as a mnemonic and clickable when paused.

## Running it

Open `mech_sim.html` in any modern desktop browser. That is the entire installation step.

There are no build tools, no package manifests, no server requirements. Three.js (r128) loads from a CDN at runtime. The file is a single self-contained HTML document of roughly 245 KB.

If you want to host it yourself, drop the file behind any static webserver. Tested on Chrome, Firefox, and Safari.

## Architecture

Everything lives in `mech_sim.html`. The file is organized roughly in this order:

1. Inline CSS (lighting palette, HUD, panels, overlays, mini-games, weather, NVG, control console).
2. Inline HTML (HUD frames, badges, overlays, start screen, game-over, pause).
3. One inline `<script>` containing:
    * Scene setup, lighting, fog, sky, mountains, smoke pillar.
    * Player state and physics.
    * Procedural world (mulberry32 PRNG, biome assignment, chunk load/unload, POI builders, prop builders).
    * Coral, Kailey, allied mechs, drone, diagnostics, mini-games, scan, logbook, comms, news wire.
    * Day/night cycle and NVG overlay.
    * Input (keyboard, mouse, on-screen console).
    * Main loop.

The file is intentionally one document. Editing happens in place. Loading is one HTTP request. State resets cleanly on restart.

### Rendering

Three.js r128, MeshStandardMaterial throughout, one directional light (the sun), one ambient light, FogExp2. No post-processing pipeline. NVG and weather effects are CSS overlays composited over the canvas. The cursor reticle is an inline SVG element following the mouse.

### Procedural generation

* `mulberry32` PRNG seeded by chunk coordinates plus a salt for deterministic regeneration.
* Two-octave coarse noise picks biomes so they form blobs rather than checkerboards.
* POI metadata persists in a Map keyed by `chunk#index`, so reloading a chunk recovers the same names and types. Tree, rock, and prop placement is regenerated from the chunk seed each load.
* Obstacles inside chunk bounds are removed on unload so collision stays consistent with what is visible.

## Design notes

The goal was to make something quiet to walk around in. Engineering ASMR is the operative phrase. Lots of readouts to look at, lots of numbers that wobble in pleasing ways, a friendly voice on the radio, a dog at your feet, a sky that changes slowly. Combat exists but is rare and easy. The sentinels stay passive unless you bother them. The mech regenerates HP. Damage routes to subsystems that you repair through small relaxed mini-games.

Naming was lifted unapologetically from LOST and Fallout 76 because those two universes already share an Appalachian-adjacent, post-collapse, anomalous-numbers vibe and combining them produces names that feel right with no further work.

The control scheme is deliberately tabletop. No FPS mouselook, no pointer lock, no twitch response. You turn with the arrow keys. You aim with the cursor. You can sit back and let the mech walk to a waypoint while you watch the weather change.

## Influences

* Fallout 76 (Appalachian setting, vault language, retro-tech reclamation aesthetic)
* LOST (DHARMA stations, the numbers, the chimes, the hatches, the bamboo)
* Death Stranding (the walking, the radio chatter, the quiet middle distance)
* Hardspace: Shipbreaker (technical readouts, voice-only crew, repair as ritual)
* Outer Wilds (gentle exploration, small voice notes, weather)
* Truckers' CB radio (Channel 47, the news wire, the bored regional comms)

## File

* `mech_sim.html` (one file, around 245 KB, no dependencies bundled)

## License

GPL-3.0
