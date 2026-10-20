# Tsunami Surf

A single-file three.js surf game: ride a 290–530 m wave as it peels down the line. Open `index.html` in a browser (it loads three.js r128 from cdnjs and the Barlow Condensed font from Google Fonts).

## Controls

| Action | Keyboard | Phone |
| --- | --- | --- |
| Lean into a carve | ← / → (A / D) | Put your thumb down anywhere on the water and drag sideways (a floating thumb-stick; further = harder) |
| Pump for speed | hold ↑ (W) | hold the big PUMP button |
| Stall (dig the tail in, slow down) | ↓ (S) | pull the thumb-stick down |
| Change camera | C | Camera button (top centre) |
| Pause / end the ride | P | II button |

The touch scheme follows how mobile surf games like True Surf work: you drive the board with a thumb on the wave rather than with buttons, so the four on-screen buttons became one floating analog stick plus a hold-to-pump button.

The rider has weight. Your input drives their lean through a spring, so they take a beat to commit and settle with a little give. The lean sets the rail, and the rail sets the turn, with wider arcs the faster you go. Let go and the board carries its line. Board and rider bank into turns, the legs load up in hard carves, and the arms swing when you change edge. Holding pump starts a steady compress-and-extend rhythm: each compression drives the board, and the board bobs and pitches under the rider.

There are no warnings or instructions on screen during a ride, only small score pops for barrels, airs and cutbacks. Ride the tube as deep as you like. Get caught behind the break and the whitewater picks you up and carries you back out. The only wipeout is the lip landing right on top of you in the trough. Rides go on until you end them from the pause menu.

## Cameras

- **auto** (default): on desktop, a director that cuts between the chase cam and a helicopter shot, a fly-by, and a low shot from the trough, going into the tube while you're barrelled. On a phone it stays on the chase cam (and the tube), so the rider is always big enough to see.
- **chase / close** (landscape): pull back and widen with speed, kick wider when you pump, and swing round behind you when you cut back toward the curl; the lens shakes at high speed and under the lip.
- **chase / close** (portrait phone): a close third-person camera behind the board that swings round after you with a deliberate delay. It keeps looking along the wave, so you see the line ahead or the curl pitching over you on a cutback.

The follow cameras smooth their offset from the rider, not their world position, so the turn delay never turns into the camera dropping behind at speed.
- **heli / trough / channel**: wide shots that show the whole wave, with a tag marking where you are.

## Scale

The wave model is built at `S = 12` times the original wave. Lengths scale by 12 and speeds and times by √12 (Froude scaling), so gravity, the breaking lip and the ride physics stay consistent at the bigger size. `S` is defined once in the wave model and passed to the wave shader as the `uS` uniform. Fog and the far scenery scale with it.
