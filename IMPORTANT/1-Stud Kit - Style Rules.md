# 1-stud building: STYLE (read first)

How to build Roblox environment pieces in "1-stud" style. Strict style; when unsure, look at the approved files in `references.md`, don't invent.

Other files in this folder (read only what the task needs):
- `references.md`: approved files, colours, textures, meshes, prop and structure recipes.
- `tools.md`: the check scripts (zfight, gridCheck, scaleCheck), player stand-in, previews, export.
- `large-sets.md`: how to build a whole map or big set in stages.
- `units.md`: SHELVED. Stud style is for scenery; units stay in house style. Only structures that units carry (howdahs, platforms) may use stud rules.
- `history.md`: one user's session log and why rules exist. Not rules; skip unless curious.

## The two layers (most important idea)
The look is **classic stud** (LEGO), not voxel. Two layers with different rules:
1. **STRUCTURE = messy stud, on the grid:** ground, paths, rocks, tree trunks and canopies, platforms, walls, steps, fire rings, log benches. Every part on the grid at 0/90/180/270°.
2. **PROPS = classic, placed freely:** crates, barrels, sacks, stones, planks, plants, wagons. Each prop is built axis-aligned from a few bold primitives (blocks, cylinders, meshes), then placed with free rotation (turned, tipped, lying).

Building props out of grid cells reads as voxel. Don't.

## Structure or prop? (decide before building)
- **Structure (grid):** part of the land or built into it, holds its place.
- **Prop (classic, free):** anything a person could pick up, move or knock over, including carts and wagons.
- If unsure, ask. Mixed pieces split into both (campfire = grid stone ring + grid logs; props around it).

## Scale (studs)
- **Reference = the standard R6 player, 5 studs tall.** Head top 5, shoulder ≈ 4, hip 2, legs 1 wide.
- **Room to stand:** ≈ 4 studs between a hazard (fire) and a seat edge; 3+ studs of walkway between props.
- Seat height 2, table 3, door 4 × 7 (≥ 3 × 6), fence/railing 3, wagon bed ≈ 2.5.
- Structure cells are 1×1×1 cubes. Ground level steps are 0.5.
- **Half studs are allowed for anything** (sizes and positions in 0.5 steps), with one limit on sizes: a part may have at most ONE dimension of 0.5, and then at least one other dimension must be 1 or more (a rail 30 × 1 × 0.5 is fine, 30 × 0.5 × 0.5 is a thin stick and not allowed). Plates for ground cover stay exempt.
- Living tree ≈ 18 (3–4 players).
- Props: author on clean numbers sized against the player (true scale). No global scale factor.

## Hard rules (both layers)
- **No z-fighting, structure on grid, scale checked:** run the scripts in `tools.md`, never judge by eye.
- **Materials:** Plastic or SmoothPlastic. **No Neon for now.**
- **Banned always:** X/cross bands built from parts (crossed bars or slabs). Weld-texture X marks are fine anywhere.
- **Bolts depend on the build:** not on nature or rustic camp pieces; allowed on mechanical builds (machines, Tinkerer metalwork, gantries, mechs) when they fit. Use the kit nut (`K.nut`, references.md), never extra parts.
- **Ground top is y = 0.** Nothing floats or sinks wrongly.

## Trusses (a core primitive)
Trusses sit with blocks, wedges and cylinders as fundamentals, more central than meshes. **Man-made things only, never nature** (no truss trees, rocks or terrain). Use them for supports, posts, scaffolds, towers, gantries, cranes, mechanical frames, ladders, railings, wherever they look right on built things.
- TrussPart is always 2 × 2 in section, length in 2-stud steps (Roblox forces this). Plan around the 2-stud module.
- Structure trusses stay on the grid (90° only); `gridCheck` covers them.
- Colour like set pieces: one tone, usually the metal `#5b5d69` or the dark trim `#4a3b31`. No textures (Studs/Weld/Inlet don't suit the lattice).
- Players can climb trusses, so a vertical truss doubles as a ladder. Mind that when placing them where climbing would break the map.
- Kit: `K.truss(group, name, length, pos, colour, { rx, ry, rz, style })`; `style` 0 Frame, 1 Alternating, 2 Bridge, 3 NoSupports.

## Detail philosophy
- **Multi detail, not singular detail:** detail comes from many simple parts together (the scene), never from detailing one part (a rim on a wheel, seams on a crate, a lip on a pot). Each piece stays plain; the whole reads as detailed.
- **Silhouette over everything**, especially from afar. Clean bold outlines; no notches, recessed corners or crossing slabs. **At map scale too:** big sets get their silhouette from composition (a few big shapes, contrast, open space), never from more parts. See `large-sets.md`.
- **Chunky, one feature:** short blocks at stud sizes over long thin parts; let one feature carry a piece (the fire carries a campfire).
- **Every part is 1-stud style, even small ones:** tongues, handles, axles, stands, braces are clean blocks in half-stud sizes, never thin odd-sized sticks.

## Colour
- **Colour budget (user, coast lesson):** 1–2 tones per material at any scale. The second is a darker shade of the first on about 10% of the area, so large masses merge into few parts.
- **Nature** (ground, rocks, trees, bushes): 2–3 close tones per material, mixed per block. Accents in recesses.
- **Set pieces** (tents, platforms, walls, furniture, fire rings, wagons): **one tone per material**, two at most (a darker trim). Texture carries the variation. Tone-mixing on built things reads as voxel.
- Muted palette only; nothing saturated. Exact colours in `references.md`. The kit's 32 classic colours (`src/fullkit-catalog.json` palette) are the source for new set-piece colours.

## Textures (Studs, Weld, Inlet)
- Accents to make things pop, not spam. No fixed caps; judgment.
- **Studs:** moss, raised grass, rock tops, some leaf tops, loose bricks, and **the dirt/mud ground (clean Studs everywhere)**.
- **Weld:** built or worked things. **Wood always carries Weld:** a one-part wood object (plank, log) is Weld all over; a multi-part one gets Weld on some parts (barrel bands, crate body). **Trees always get Weld splotches on trunk/roots/limbs**, never leaves.
- **Inlet:** the quiet texture for flat built surfaces (decks, floors, wagon beds, paving, walls).
- **Cylinders take textures well** (user, corrected): Weld, Studs and Inlet all sit cleanly on true cylinders (a quilted diamond pattern on a tower drum looks right). Use them like on blocks: Weld on worked/wood/metal things, Studs on nature tops. The old "no textures on cylinders" rule is dropped. **No Weld on the ground.**

## Structure: messy stud
- Curves, tapers and diagonals come from **stepping**. Detail from repetition and parts 1 stud proud.
- **Wedges** round off grid shapes (hanging wedges under a log bench) and stand in for **45°** (roof pitch, wall brace, stair stringer). Prefer this to rotation.
- **Messiness ≈ 6/10, a little heavy:** outlines jut and step, overlapping rects in different tones (nature only).

## Terrain: cliffs and rock masses (approved: `sand-cliff.js`)
- **Build from a heightmap of stamped rects**, not cell by cell: each rect sets a column height (max wins) and one tone from 2–3 close tones. Outlines step and jut on their own.
- **Massifs step back and up in tiers** (3–4 offset rects per tier), with **jutting columns** (1–3 wide, 1–2 proud) standing on the tier below and stopping short of, or 1 above, the tier top. The columns give the vertical rhythm.
- **Face detail is flush:** Inlet or Weld panels are recoloured cells set into tall faces (2–3 wide, 2–4 tall), never proud slabs. A few per massif.
- **Moss:** 0.5 Studs plates on plateaus, plus 1-wide Studs drips running down the front faces from the moss edge. Moss carries most of the colour contrast.
- **Feet:** sloped wedges at the base of some faces, short upright cylinder stubs on the sand beside them.
- **Routes cut into the rock:** stairs are carved through the masses (rock rises on both sides), 1 rise per stud, in a pale tone that contrasts with the rock.
- **Ground:** Studs sand, low Studs dune plates, a few pebbles. Plants (Fern/Bush meshes) only on moss.

## Props: kit meshes FIRST (user, snow camp)
**If the kit has a mesh of the exact thing (barrel, bucket, teapot, mug, snowman, wreath, torch, rock, tin pot, candle…), use it** (`K.mesh`, catalog in `references.md`). The kit meshes are the official 2000s–2010s Roblox meshes, and that early-Roblox look is essential to 1-stud style. Only build a prop from primitives when no mesh matches. The old "no barrels or crates from primitives" note never meant "no barrels": search `src/fullkit-catalog.json` before every prop. Some kit meshes import UPSIDE DOWN and need rx 180 (Bowl, Snowman: the user confirmed "snowmen are upside downers"; the Snowman's 2.6 Z is its arm span). Check other meshes with the user before relying on them.

## Props: classic
- **One construction language:** a plain body plus proud parts (bands, posts, rails) at simple fractions (≈ 1/16–1/8 of the width proud per side). Every prop looks like it came from the same hand.
- **Detail from material and colour, not geometry.** No drawn seams, bungs, rims, tyres.
- **Rotation = whole props only (for now).** A finished prop may be turned or tipped when placed. Don't build things out of individually rotated blocks or cylinders (teepees, tripods, ropes, leaning sticks, log rings). Build those on the grid.
- **Never step a round shape.** A round object is one clean primitive (the box barrel) or a true cylinder/round mesh (wheels, cogs, pots). Stepped circles read as voxel from afar. A cylinder axis-aligned in its object (a wheel on its axle) is fine.
- **Things people always picture as round are round, even in structures** (user, temple): columns, shafts and fallen drums are true cylinders (Rz 90° for upright, centre on a quarter stud, textures allowed) on square stud-block plinths and capitals. Statue heads use the scaled-up rounded-cylinder Head mesh (`ClassicKit.round`, in group `Props/...`). Blocky versions read as pixel art.
- **Ask first:** whenever a part could read as voxel if built blocky (wheels, cogs, pots, tabletops, lanterns), ask "should this be round or not?"
- **Overlap freely**, as long as no faces are coplanar.

- **Kit meshes can import rotated or upside-down** (Bowl does). Flip on placement and draw the preview stand-in to match; never fill a mesh container with primitives.
- **Greens for living things only:** vines and moss are leaf greens, not brown roots. Foliage meshes: Bush and Sprout.

## Working with the user
- Build small, one piece per file plus a preview. Big scenes follow `large-sets.md`.
- When the user sends a reference model, measure it (parse the rbxmx) and state differences before fixing. Then write the lesson into the right file here.
- Small targeted changes when asked. Terse replies.
- New lessons: rule → this file; asset/recipe → `references.md`; tooling → `tools.md`; big-set method → `large-sets.md`; the story of why → `history.md`.

## Checklist before export
- **Terrain finishing (nothing generates these on its own, add them on purpose):** scree wedges at the foot of tall faces, wedge chamfers/caps on stepped banks and drift edges, flush pebble discs along paths and banks, flush panels or drips on featured faces. Snow camp skipped them in its first dressing pass.
- zfight = 0, gridCheck = [], scaleCheck = [] (or warnings explained). See `tools.md`.
- Looked at in the Eye view with the player on; ¾, close, low and top views; textures on and off.
- No part-built X bands ever; no bolts on nature/rustic pieces; no Weld on the ground, no stepped circles.
- Colours from the palette; set pieces one tone per material.
