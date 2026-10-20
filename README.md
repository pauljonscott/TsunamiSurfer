# Tsunami Surf

A single-file three.js surf game: ride a 150–260 m wave as it peels down the line. Open `index.html` in a browser (it loads three.js r128 from cdnjs and the Barlow Condensed font from Google Fonts).

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Carve up the face / down the face | → / ← (D / A) | ▶ climb / ◀ drop, or drag sideways |
| Pump for speed (uses your legs meter) | ↑ (W) | ▲ pump, or drag up |
| Stall (dig the tail in, slow down) | ↓ (S) | ▼ stall, or drag down |
| Change camera | C | Camera button (top centre) |
| Pause | P | — |

Carving sets your turn rate: hold it to keep turning, let go and the board settles back to trim. Dropping down the face gains speed and climbing costs speed. Pumping drains your legs; run them flat and you have to cruise until they recover.

## Cameras

- **auto** (default): a director that cuts between the chase cam and a helicopter shot, a fly-by, and a low shot from the trough. It goes into the tube while you're barrelled, switches to the helicopter shot for airs, and drops back to the chase cam when you're in trouble.
- **chase / close**: pull back and widen with speed; the lens shakes at high speed and under the lip.
- **heli / trough / channel**: wide shots that show the whole wave, with a tag marking where you are.

## Scale

The wave model is built at `S = 6` times the original wave. Lengths scale by 6 and speeds and times by √6 (Froude scaling), so gravity, the breaking lip and the ride physics stay consistent at the bigger size. `S` is defined once in the wave model and passed to the wave shader as the `uS` uniform.
