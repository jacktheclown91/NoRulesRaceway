# Spectrum Sprites: No Rules Raceway

**6 Sprites. 3 laps. Zero rules.**

A js13kGames 2026 arcade combat kart racer set in Prismara.

You pick Pip, Rill, Moss, Zip, Mimi or Lux, then spend three laps drifting, ramming, jumping, grabbing mystery-box items and generally behaving like the track owes you money.

## What made it into 13K

- six playable Spectrum Sprites with distinct procedural silhouettes
- six-racer AI field with passing and physical kart contact
- manual acceleration, braking and high-risk drifting
- drift charge into mini-turbo / Spectrum Momentum
- seeded procedural courses with hills, drops, bends, bridges and ramps
- one coherent Prismara panorama per course
- terrain projected from the same road geometry so the track actually belongs to the world
- sparse mystery-box pickups instead of item walls
- Prism Disc, Spectrum Peel, Burst Crystal and Seeking Disc
- visible target warning; committed drifting can dodge a seeking attack
- lap-to-lap course mutation and painted race history
- procedural WebAudio for engine, boost, pickups, warnings, hits, dodges and finish
- desktop and touch controls

No external art or audio files are used by the game itself. Canvas does the drawing, WebAudio makes the noise, and the packer does increasingly questionable things to the JavaScript until the ZIP behaves.

## Controls

- **W / Up** — accelerate
- **S / Down** — brake
- **A / D or Left / Right** — steer
- **Space** — hop / hold to drift, release for a charged boost
- **E / Ctrl** — use held item
- **H** — show controls
- **R** after the finish — new track
- **C** after the finish — character select

Touch controls are drawn on-screen.

## Build

```bash
npm install
npm run build:check
```

The release builder bundles with esbuild, runs Terser, Roadroller and Zopfli, writes `dist/game.zip`, and fails if the final ZIP is larger than **13,312 bytes**.

The release candidate used for submission is roughly 13.0 KB zipped, depending on the compressor search result.

For a local source build:

```bash
npm run serve
```

Then open the local URL it prints.

## Source layout

- `src/main.js` — race loop, input, camera, HUD and handling
- `src/track.js` — course generation, road, terrain and scenery
- `src/characters.js` — Spectrum Sprites and kart rendering
- `src/items.js` — pickups, attacks and item HUD
- `src/pack.js` — pack racing / contact helpers
- `src/laps.js` — lap mutation
- `src/audio.js` — tiny procedural sound system
- `tools/build.mjs` — the 13K meat grinder

Built for js13kGames 2026. The game is small. The amount of arguing required to make the road stop deforming at the bottom of the screen was not.
