# Otter Loader

A dot-grid loading animation with a success transition. One HTML file, no dependencies.

- **Default state, "Scan bounce, soft":** a band sweeps down the otter and back up, easing into each turn inside the otter. Each dot's brightness is set by how many beats ago the band last crossed it, so the trail follows the band through the turn. Shaded mono keeps the eyes and outline brightest and the muzzle softest.
- **Success state, "From the muzzle, soft":** on succeed the band and its trail fade out over eight beats while a deep blue grows out from the left of the muzzle with a wide, soft front. Dots the blue has not reached settle to a dim rest. The blue holds until reset.

Grid 36 x 36, one beat = 52 ms. Everything is defined in beats, so it looks the same at any canvas size.

The container is a 1px `#525252` stroke at 30% opacity, outside the box, with 12px corners, 4px padding and no fill. The grid inside has 8px corners so the two radii stay concentric, and they clip the background dots that fall past them.

Text under the animation, 24px below it: header Inter Semi Bold 20, line height 125%, letter spacing -1%; description Inter Regular 14, line height 150%, letter spacing -0.75%; 4px between them.

## Try it

Open `index.html` in a browser. It shows the tapping state, the tapping success state, and a third card that cycles from one to the other, each with its header and description text.

## Use it

Copy the `OtterLoader` script block into your page, give it a square `<canvas>`, and call:

```js
const loader = OtterLoader(canvasElement); // starts scanning
loader.succeed();                          // play the success state, holds blue
OtterLoader(canvasElement, {pad:0.1});     // optional margin around the grid (default 0)
loader.reset();                            // back to scanning
loader.destroy();                          // stop the animation clock
```

Colours, beat length and grid size are constants at the top of the script.
