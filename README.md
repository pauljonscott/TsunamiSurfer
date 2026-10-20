# Tsunami Surf

A single-file three.js surf game: ride a 290–530 m wave as it peels down the line. Open `index.html` in a browser (it loads three.js r128 from cdnjs and the Barlow Condensed font from Google Fonts).

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Carve (turn the board) | ← / → (A / D) | ◀ / ▶, or drag sideways |
| Pump for speed (uses your legs meter) | ↑ (W): tap for a burst, hold to keep driving | ▲ pump, or drag up |
| Stall (dig the tail in, slow down) | ↓ (S) | ▼ stall, or drag down |
| Change camera | C | Camera button (top centre) |
| Pause | P | — |

Carving sets your turn rate: hold it to keep turning, let go and the board settles back to trim. The board turns all the way round, so you can cut back toward the curl and come round again down the line (a cutback scores more the closer to the pocket you do it). Steering is relative to the board: heading down the line, → climbs; cutting back, → drops. The touch buttons relabel themselves to match.

Dropping down the face gains speed and climbing costs speed; speed carries (low drag), so plan your turns. Each press of pump kicks the board forward (about 50 km/h) and holding it keeps driving. Both drain your legs; run them flat and you have to cruise until they recover.

Trimming mid to high on the face holds the pocket. Sit low or deep and the curl slowly catches you: "Too deep! Pump!" warns you well before the tube closes out, and pumping gets you out.

## Cameras

- **auto** (default): a director that cuts between the chase cam and a helicopter shot, a fly-by, and a low shot from the trough. It goes into the tube while you're barrelled, switches to the helicopter shot for airs, and drops back to the chase cam when you're in trouble or cutting back.
- **chase / close**: pull back and widen with speed, kick wider when you pump, and swing round behind you when you cut back toward the curl; the lens shakes at high speed and under the lip.
- **heli / trough / channel**: wide shots that show the whole wave, with a tag marking where you are.

## Scale

The wave model is built at `S = 12` times the original wave. Lengths scale by 12 and speeds and times by √12 (Froude scaling), so gravity, the breaking lip and the ride physics stay consistent at the bigger size. `S` is defined once in the wave model and passed to the wave shader as the `uS` uniform. Fog and the far scenery scale with it.
