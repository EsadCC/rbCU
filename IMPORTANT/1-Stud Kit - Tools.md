# 1-stud building: TOOLS

All checks run in a run_script, never by eye. Load modules with
`new Function('module','require','window', src)(m, (n) => mods[n.replace('./','')])` in dependency order:
block-kit → stud-kit → forest-1stud → forest-corner → classic-kit → the piece.

## Checks (all in block-kit.js)
- **`zfight(parts)`** must return []. Same-facing coplanar overlaps. Stacked or crossed pieces need an offset ≥ 0.03.
- **`gridCheck(parts, { skip: ['Props', …] })`** must return []. Structure only: rotation a multiple of 90°, x/z edges on half studs, y edges on 0.1 steps, round parts on a quarter-stud point. Skip prop groups (and prop-built set pieces like `Wagon`).
- **`scaleCheck(parts, { doors, walk })`** must return [] or each warning explained. Seat tops 1.5–2.5 (groups named Bench/Seat/Stool), ≥ 4 from Fire/Ash groups to seats, prop heights (`PROP_H`: Barrel, Sack, Plants, Pot), doors ≥ 3 × 6 (`build()` may return `doors: [{name, w, h}]`), ≥ 3 clear for `walk` pairs.
- **Group naming** so checks can read it: seats contain Bench/Seat/Stool, hazards Fire/Ash, props `Props/<Kind>`.

## Overlap (volume) check: run for props, not only z-fighting
`zfight` only catches coplanar faces. For props use an OBB-vs-OBB separating-axis test over all `Part` boxes (15 axes: 3+3 face normals, 9 edge crosses); report any pair whose minimum penetration is above 0.02, and skip Ground/Terrain groups when props stand in ground cover. Crates and barrels must report 0 against everything else.

## Player stand-in and views
- `BlockKit.player(at, ry)`: a 5-stud R6 figure, preview only, never exported. A piece's `build()` may return `player: [x, z, ry]` to stand it where a player would be.
- **Eye view:** first-person at eye height 4.5, 70° FOV like Roblox. Judge pieces from there, not only from orbit.

## Previews
- Copy an existing preview (`Wagon.dc.html` is the newest): fake Studs/Weld/Inlet canvas textures with per-face stud UVs, Textures and Player toggles, view presets, rbxmx download, check results in the info line.
- `window.__view` (orbit) and `window.__draw()` (redraw now) for stills when animation frames are throttled.

## Kit primitives (block-kit.js `kit()`)
`box`, `wedge`, `truss` (2 × 2, length in 2s, `style`), `nut` (bolt head, mechanical only), `mesh` (kit MeshPart from `src/fullkit-catalog.json`), `add` (anything, incl. cylinders `shape: 2`), `lbox`/`beam` (local-frame helpers).

## Export
- `BlockKit.toRbxmx(model, { rootXml })`: pass the MaterialVariants from `src/material-variants.json` as rootXml so Studs/Weld/Inlet export at the root.
- One file per piece; a layout file assembles them later.
