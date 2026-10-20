# Tsunami Surf

A single-file three.js surf game: ride a 290–530 m wave as it peels down the line. Open `index.html` in a browser (it loads three.js r128 from cdnjs and the Barlow Condensed font from Google Fonts).

## Controls

| Action | Keyboard | Phone |
| --- | --- | --- |
| Go that way | arrows / WASD point on screen | put your thumb down anywhere and push the way you want to go (a floating thumb-stick) |
| Pump for speed | hold Space | hold PUMP |
| Stall (dig the tail in) | hold Shift | hold STALL |
| Change camera | C | Camera button (top centre) |
| Pause / end the ride | P | II button |

You point where you want to go and the board carves round to follow. It turns harder the further you push, and arcs get wider at speed. Let go and it holds its line. Directions are read through the camera: in the chase cam, up the screen is along the wave and sideways is up or down the face. Nothing steers the board except you.

Go anywhere. Cut back into the curl, ride as deep in the tube as you like, or carry speed up an unbroken crest and over the top: you either launch an air or slide over and down the back. Airs land wherever you come down. A pitching lip is a ceiling you scrape along, from the front or from behind. Run out of speed climbing the wall and the board stalls and falls back round.

The only wipeout is the lip landing right on top of you in the trough. Slide off the back into the flats and the ride ends. Otherwise you ride until you end it from the pause menu.

The board sits in the water and draws a foam line on the face behind it. There is no HUD clutter: score, speed and wave height, plus small score pops for barrels, airs and cutbacks.

## Cameras

There is one steady camera at a time and it never cuts on its own.

- **chase** (default): behind the surfer, looking along the wave, with the wall on one side and the open ocean on the other. It doesn't turn with the board; it swings round only once you commit to a cutback. Its position trails your turns (you feel the delay), but its aim stays locked on the rider, so you never leave the frame.
- **side**: a water photographer's angle, out in front of the face and down the line, looking back at the rider with the wall behind them.
- **heli**: a helicopter shot of the whole wave, with a tag marking where you are.

## Scale

The wave model is built at `S = 12` times the original wave. Lengths scale by 12 and speeds and times by √12 (Froude scaling), so gravity, the breaking lip and the ride physics stay consistent at the bigger size. `S` is defined once in the wave model and passed to the wave shader as the `uS` uniform. Fog and the far scenery scale with it.
