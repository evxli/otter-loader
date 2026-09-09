# Otter Loader

A dot-grid loading animation with a success transition. One HTML file, no dependencies.

- **Default state, "Scan bounce, soft":** a band sweeps down the otter and back up, easing into each turn inside the otter. Each dot's brightness is set by how many beats ago the band last crossed it, so the trail follows the band through the turn. Shaded mono keeps the eyes and outline brightest and the muzzle softest.
- **Success state, "From the muzzle, soft":** the scan stops, the grey dots rest dim, and a deep blue grows out from the left of the muzzle with a wide, soft front. The blue holds until reset.

Grid 36 x 36, one beat = 52 ms. Everything is defined in beats, so it looks the same at any canvas size.

## Try it

Open `index.html` in a browser. Use the Succeed and Reset buttons.

## Use it

Copy the `OtterLoader` script block into your page, give it a square `<canvas>`, and call:

```js
const loader = OtterLoader(canvasElement); // starts scanning
loader.succeed();                          // play the success state, holds blue
loader.reset();                            // back to scanning
loader.destroy();                          // stop the animation clock
```

Colours, beat length and grid size are constants at the top of the script.
