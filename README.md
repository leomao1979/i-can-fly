# I Can Fly

A small browser game: take off from any address and fly over the real world.

The scenery is Google's photorealistic 3D map, streamed through Cesium. Near the ground, where the 3D model looks rough, you can land in Google Street View and walk along the street, then take off again.

The whole game is one file, `index.html`. There is nothing to build or install.

## What you need

| Key | Required | Used for | Where to get it |
|---|---|---|---|
| Cesium ion access token | Yes | 3D scenery, terrain, address search | [ion.cesium.com/tokens](https://ion.cesium.com/tokens) (free account) |
| Google Maps API key | No | Landing in Street View | Google Cloud console, with the **Maps JavaScript API** enabled |

Both keys are typed into the game's start screen and saved only in your browser. They are never written into the file.

Notes on the Google key:

- It needs a Google Cloud billing account. Dynamic Street View has a free monthly allowance; each start or landing in Street View uses one panorama load.
- You do not need a Google Maps subscription plan.
- If you open the game as a local file, do not add a website restriction to the key, or Google will reject it. Restrict it to the Maps JavaScript API instead.

## How to play

1. Open `index.html` in Chrome or Safari (double-click it, or host it with GitHub Pages).
2. Paste your Cesium token, and optionally your Google Maps key.
3. Type an address, a landmark, or coordinates such as `37.8199, -122.4783`, and press **Take off**.

With a Google key you start standing on the street in Street View. Without one you start on the ground in the 3D view.

## Controls

### Flying

| Keys | Action |
|---|---|
| `W` `S` | Speed up / slow down |
| `A` `D` or `←` `→` | Turn left / right |
| `↑` `↓` | Tilt flight path up / down |
| `Space` `Shift` | Rise / sink straight up or down |
| Drag mouse, or `I` `J` `K` `L` | Move your eyes |
| `G` / `V` | Look straight down / look ahead again |
| `H` | Stop and hover |
| `E` | Land in Street View |

### In Street View

| Keys | Action |
|---|---|
| Click the arrows on the road | Walk |
| Drag mouse, or `I` `J` `K` `L` | Look around |
| `Space` | Take off |

## Scenery

The **Switch scenery** button toggles between:

- **Photorealistic 3D** (default): Google's textured 3D model built from aerial photos.
- **Terrain + plain buildings**: real terrain with satellite imagery and untextured building shapes. The game falls back to this if the photorealistic data is unavailable.

## Limits

- An internet connection is required; the map data streams live and cannot be downloaded.
- The 3D model is built from aerial photos, so it looks best from about 50 m up and rough at street level.
- Street View exists only where Google has street photos. The game looks within 300 m of where you are.
- Cesium's free Community plan covers personal, non-commercial use.
