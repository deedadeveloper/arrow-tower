# Arrow Tower

A mobile-friendly 3D "tap the arrows" puzzle on a spinning tower. One file (`index.html`), Three.js from a CDN, no build step.

**Play:** open `index.html` in a browser (needs internet for Three.js), or serve the folder / host it on GitHub Pages.

## How to play
- **Drag left/right** to spin the tower (touch or mouse, with inertia).
- **Tap an arrow** to launch it. It only flies off if its path is clear:
  - **Up / Down** arrows need every tile above / below them in the same column to be empty.
  - **Left / Right** arrows need every tile in their row between them and the **gold seam** to be empty. The tower's ring is cut at the seam: left arrows run toward the column-0 side, right arrows toward the last column.
- Tapping a blocked arrow shakes it (the blocker flashes too) and costs a heart. You get 3 hearts per level.
- Clear every arrow to win. Levels are endless; progress is saved in `localStorage`.

## Levels
Each level is generated from a seeded RNG by placing arrows in *reverse removal order*: every new arrow gets a direction whose path is clear of the arrows already placed. Removing them in reverse order is always legal, so every level is solvable. Difficulty (rows 5→14, columns 6→12, fill 50%→72%) grows with the level and caps around level 19.
