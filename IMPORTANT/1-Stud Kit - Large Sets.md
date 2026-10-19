# 1-stud building: LARGE SETS (maps, lobbies, big scenes)

Three good pieces stitched together looked like a month-long showcase, not a lobby. Pieces built alone are over-detailed for a map.

## Why stitched showcase pieces fail as a map
- **Detail is spread evenly:** clutter, Studs and tone-mixing everywhere at the same density, so nothing reads as important.
- **Each piece on its own plot:** separate dirt yards read as exhibits, not one place.
- **One height:** nothing for the eye to climb, no framing.
- **No paths or edges:** nothing connects pieces; the map ends at a slab edge.

## Composition first (user: "not by just more")
Lobbies and maps are not showcases. A big set needs a strong silhouette just like a small piece, and it gets one from **composition**, not added detail.
- **Big shapes read first:** 3–5 large masses with clear outlines should make the place recognisable from a distance and from spawn, before any texture or clutter. If the blockout doesn't read, dressing won't fix it.
- **Big / medium / small:** most of the area is big quiet shapes (flat ground, plain cliff walls); medium shapes break the big ones at chosen spots; small detail only where the player stops or looks.
- **Contrast does the work:** tall against flat, open against enclosed, plain against busy, light against dark. Detail matters because of the plain areas around it.
- **Negative space is designed:** open flats, sky gaps and sightlines are part of the composition. Don't fill them.
- **Test:** squint at the overview and the spawn view with textures off. If it reads as noise or as even bands, rework the shapes. Don't add parts.

## Principles
1. **Density hierarchy:** quiet base ground (one tone, sparse clutter) over most of the map; detail clustered at focal points and fading outward.
2. **Height:** terraces, stepped cliff edges, ramps and stairs, a raised spot for a key piece, sightlines from spawn.
3. **Paths and flow:** worn routes linking spawn to each point, wide enough for groups (≥ 6), shared dirt instead of a yard per piece.
4. **Framing:** dense trees or rock walls at the borders so the map closes in on itself.
5. **Budget:** a rough part count per zone so a lobby stays a lobby.

## Build in stages (never all at once)
Building blind (numbers first, screenshots after) means one bad call spreads into everything on top of it. Each stage is its own file building on the last, approved before moving on:
1. **Blockout:** terrain heights, cliffs, paths and zones in plain grey, with the player stand-in. Approve flow and scale.
2. **Key spots:** focal pieces placed in their zones, kept simple.
3. **Terrain dressing:** grass tones, Studs, edges, framing trees and rocks.
4. **Props:** clusters around key spots, density fading outward.
5. **Polish:** all checks, budget count.

Going back to fix a stage doesn't wipe later work. Approved stages become fixed inputs.

## Lessons (sandy coast, first big set)
- **Dressing can't hide a contour blockout.** Three even 8-stud bands following one front line still read as a blockout after texturing, columns and moss. The massing itself needs the cliffside method at map scale: many overlapping massifs (stamped rects, tiers 3–5 studs, varied footprints), so the shapes vary before any dressing.
- **Budget:** a 200×200 set in this style needs far more than 8k. The landmarks and 13 small trees alone came to about 2.7k. Agree a budget per zone up front.
- **Ask for species and biome up front** (palms vs oaks, bonsai). Tree style follows the setting.
- **v2 overcorrected (massifs stamped everywhere):** too messy, nowhere to walk off the paths. **Massing goes on the EDGES only** (cliff faces, rims, map borders, around landmarks). Lay out the walkable flats first (terraces, plateaus) and keep them open; break up the layering only where flats meet drops.
- **High flats get grass ground** (full cover on the walkable top, frayed at the rim), not scattered moss specks ("green acne"). Moss is an edge accent (drips, rim lips).
- **Tones: 1–2 per material.** The second tone is always a darker shade of the first, on about 10% of the area. That lets big masses merge into few parts. Random tone rects everywhere were the main part spam.
- **Vertical streaks** come from heightmap columns (one box floor-to-top per cell run) cut by thin stamps, jutting columns and 1-wide drips. Fewer, larger stamps; sparse columns; drips only on featured faces.
- **Preview at 10k+ parts:** merge static geometry per material and run zfight after the first frame (it takes ~10s at 10k).

## Lessons (sandy plateau, first completed big set)
Scope that worked: ONE landmark + a 100×100 plot, five approved stages (blockout → temple → dressing → props → polish), ~3.4k parts, 0 z-fighting, grid and scale clean.
- **Plot shape:** beach arrival (0) → terrace (6) → plateau (12) with the landmark across the whole back; cliffs only on the back and one side, west and front open. Stairs 6 wide (1 rise per stud, 6–7 rises per flight), paths 6 wide, a loop route back down.
- **Landmark dominates:** a "temple" that spans the plot width (64 of 100) and stands twice the cliff height reads as a landmark; a 24×18 display piece did not. Collapse one side (east) so it isn't symmetric.
- **Flats = sand cap on a rock body:** walkable tops are a 1-stud Studs sand cap with frayed rims; rock tone only on faces. Massing (tiered stamps, jutting columns, flush panels, moss + drips, scree) only on the back wall, the east massif and a backdrop ring beyond the plot that tapers to the open west.
- **Budget split used:** terrain + massing ~1.6k, temple ~0.7k, palms ~0.85k (8 palms), props ~0.2k, cover/moss ~0.5k. Uncapped budget was spent where the eye lands.
- **Generators need variety knobs:** the first palm function made clones. Per-instance kind (young / normal / tall / twin), bend steps, frond count / length / droop profile, lean bias, nuts. Wood gets Weld splotches, leaves Studs splotches, plus wedges and balls.
- **Props story first:** "left in a hurry, sea and jungle taking it back" set every prop (grain store, offerings, toppled idol head, slab with marks, vines). Clusters at the temple and stair route, nothing evenly scattered.
- **Kit meshes:** lean on them for props (see references.md). The preview needs a stand-in per mesh name (`kitGeo`). Keep the stand-in honest to the real import orientation.
- **Pitfalls hit:** water box coplanar with terrain edge; dune plates under palm roots; two plants on adjacent cells; a pediment wider than the wall under it (floating slab); a pediment not centred on its door.

## Lessons (snow camp, 60×60 scoped set)
Stages blockout → key spots → dressing, ~4.5k parts, zfight 0, grid [], scale []. Files `snow-blockout.js`, `snow-spots.js`, `snow-pines.js`, `snow-dressing.js`, previews `Snow Camp {Blockout,Key Spots,Dressed}.dc.html`, export `export/SnowCamp.rbxmx`.
- **Trees are the second most important thing** (user): stepped square cones / slab "cake" pines read as the common simplification and were rejected. Palm-style voxel generators (whorls of drooping fan boughs, wedge rounding) were approved ("much better"). See `references.md`.
- **Budget:** ~1,100 parts per 34-stud pine, ~600 per 26-stud. Treat tree count as the budget knob (7 pines ≈ 3.5k). Smoothing wedges are the cost: keep ~30%.
- **Put all trees in ONE shared vox (world cells)** so overlapping canopies merge instead of z-fighting. Cells must skip positions at or beside taller terrain (check self + 4 neighbours + 2 out), or they go coplanar with terrain faces.
- **Clear head height:** no foliage below 7 studs, or the Eye view at spawn is blocked.
- **Previews at ~5k parts:** merge meshes per material and defer zfight/gridCheck until after the first frame, or the page hangs.
- **Plain terrain clearing:** keep camp pieces 1.3× tree reach away from trunks so the camp stays visible from above.
- **Empty fire pit:** user supplies the flames; no logs, ash or fire. User also rejected the snowman prop as too dense for me to build.

- **Tree tops:** the trunk must end under the foliage (3-stud green spire with a snow cap); a bare trunk pole above the crown was spotted by the user.
- **Props restraint:** stage 4 was ~25 parts (tea set from kit meshes, stump, signpost, 2 logs, sprouts). User rejected the snowman as too dense; fewer, quieter props beat a full set.
- **Terrain finishing is on purpose:** pebbles were over-placed first (38 along paths and banks, user: too many, wanted a few messy strays on open ground, never on paths or deliberate spots, ~12). Wedges: user wanted MORE; scree at the foot of every tier (not only ground level, ~85%) plus half-height pond-bank wedges. Density is a knob the user tunes, so build it adjustable.
- **Verifier loop:** "viewport not ready" meant the page hung (heavy synchronous checks), not a layout bug. Defer checks and merge meshes first.

## Open (learn in the next practice builds)
- Density numbers (clutter per 10×10 in quiet vs focal zones).
- Terrace heights and cliff recipes.
- Path width and edge treatment.
- Part budgets per zone.
- Scale-check extensions: path widths, clutter density per zone.
