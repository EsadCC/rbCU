# 1-stud building: REFERENCES

Approved files, colours, textures, meshes and recipes. Rules live in `style.md`.

## Approved files (look here first)
- `block-kit.js`: `kit()` (box/wedge/truss/lbox/beam/add), `toRbxmx` (supports `variant`, mesh extras, `rootXml`), `zfight`, `gridCheck`, `scaleCheck`, `player`.
- `stud-kit.js`: `vox()` cells with greedy merge, `plates()`, colour suffix `/S` `/W` `/I`.
- `forest-1stud.js`: `livingTree`, `deadTree`, `trunk`, `branch`, `root`, `canopy`, `smooth`, `weldSplotch`.
- `forest-corner.js`: `ground`, `rock`, `pad` (bush), `stump`, `waystone`; palette `C`.
- `classic-kit.js`: props `barrel`, `crate`, `sack`, `round`, plus mushroom, stepping stones; `MESH`.
- Pieces: `campfire-v2.js` (approved: grid stone ring, grid logs inside, log benches, stump, woodpile), `tent.js` (ridge tent, 45° wedge roof), `wagon.js` (prop-built wagon, cylinder wheels).
- Previews: `Forest Corner.dc.html`, `Classic Test.dc.html`, `Campfire v2.dc.html`, `Tent.dc.html`, `Wagon.dc.html`. Copy one for new pieces (they include textures, player and checks).
- **Rejected (don't copy):** `clutter-set.js` / `Camp Clutter.dc.html` (voxel props), `campfire.js` v1 (teepee/tripod of rotated sticks), flat-pad oak, cross plates (always banned), screws on the forest pieces (bolts only fit mechanical builds).

## Structure palette (forest-corner.js `C`)
- Mud `#5a4433`. Grass `#5f7a3b` `#6a8541` `#56703a`. Moss `#7a9e45` `#6b9140`.
- Bark `#5a4232` `#4c392b` `#68503b`, cut end `#a8875f`.
- Leaf `#3d6a35` `#4a7a3b` `#345a2e` `#588a42` (dark under, light on top).
- Rock `#7d7871` `#6b665f` `#8a857d`. Pebble `#8a857d` `#6f6a63` `#5f5a54`. Brick `#857f77` `#6f6a63` `#7a5a3e`.
- Ash `#4f4a45`. Canvas `#b3a385`.
- New materials: pick 2–3 close muted tones (nature) or one (set pieces), show the user, list here once approved.

## Prop colours
Barrel wood `#5a4c42`, crate/wagon wood `#8a6a4a`, dark frame/trim `#4a3b31`, metal `#5b5d69`.

## Textures
The MaterialVariants `Studs`, `Weld`, `Inlet` (uploads/stud.rbxmx, weld.rbxmx, inlet.rbxmx) are saved in `src/material-variants.json` and exported at the rbxmx root (the user moves them to MaterialService). Parts are Plastic with `MaterialVariantSerialized`. Use `variant: 'Studs'|'Weld'|'Inlet'` or the colour suffix `/S` `/W` `/I`.

## Structure recipes
- **Living tree** (≈ 18): trunk layers 4×4 → 3×3 → 2×2 (`trunk()`: wedge on each ledge, hanging wedge under overhangs); dark bark ridges 1 proud with wedge caps; knothole with lips; wedge-capped roots; three 45° stair limbs (`branch()`); canopy crown + four masses (`canopy()`), `smooth()`; `weldSplotch` on the wood.
- **Dead tree:** same trunk with a jog and broken wedge top, stair branches ending in twigs.
- **Rock:** 2–3 stacked offset rects in grey tones, 1–2 Studs moss cells on top.
- **Bush (stud):** 2 layers of offset leaf rects, darker under. In mixed scenes prefer the Bush/Fern meshes.
- **Stump:** 2×2 core, plus-shaped flare, Weld bulge.
- **Waystone:** plain stacked Weld rock blocks.
- **Ground:** Studs mud base under 0.5 grass plates in mixed tones (some Studs), raised moss levels each +0.5 (mostly Studs); bare mud paths with frayed edges; loose 1×2 bricks and pebble cylinders, spaced apart.
- **Fire ring (campfire-v2):** one-tone grey stone ring on the grid round a 4×4 pit, corners open, a few stones stacked +1, some Studs tops; Studs ash plate; Weld logs stacked log-cabin inside.
- **Log bench:** 3 wide flat top at seat height 2, centre row under it with hanging wedges either side (rounded underside), light cut ends, one stub, Weld splotches.
- **Ridge tent (draft):** 45° roof of one wedge + one cell per row, wooden wedge bargeboards on the end rows, ridge pole under the peak, gables inset 1, door with tied-back flap columns. Door 2 × 4 fails the 3 × 6 check.
- **Rock cliffside (approved, `sand-cliff.js`):** heightmap of stamped rects (max-height wins, one tone per rect from 3 close tones); each massif = tiers stepping back and up (3–4 offset rects per tier) plus 3–6 jutting columns standing on the tier below; flush Inlet/Weld panels recoloured into tall front faces (not proud); Studs moss plates (0.5) on plateaus with 1-wide Studs moss drips down front faces; scree wedges at feet; upright untextured cylinder stubs; a pale two-tone sand stair carved through the rock; Studs sand ground with Studs dune plates. Sandstone `#a5835f` `#977657` `#b28f6a`, sand `#dcc9a0`, dunes `#e3d3ab` `#d3bf93`, stair `#e6d9b6` `#dacba2`.
- **Built structures (walls, floors, fences): NOT YET APPROVED.** References (uploads/pasted-1791137532225, 1791137578032): framed panels, raised trim 1 proud, repeated posts and rails. Build a small test piece, get approval, write the recipe here.

## Approved props (classic-kit.js, wagon.js)
- **Barrel** (true cylinders, nothing overlaps): three stacked Weld cylinders (ends 0.5 narrower than the belly) with a Weld hoop cylinder BETWEEN each pair, so a hoop never encloses the body. big (default) belly d3, ends d2.5, hoops d3.5 × 0.5, segments y 0–1, 1.5–2.5, 3–4; small belly d2, ends d1.5, hoops d2.5 × 0.5, segments 0–0.5, 1–2, 2.5–3. `barrel(K, B, small)`.
- **Crate** (LEGO-built, from the user's example `uploads/example.rbxmx`: a 3×3×3 cube with a 3×1×0.5 plate resting flat on its face): plain Weld cube s × s × s, then flat 0.5-thick plates resting on the four side faces, forming a frame per face: a full-width 1-tall strip along the top and along the bottom, and 1-wide uprights between them when s ≥ 3 (s < 2: one flat s × s plate per face). Footprint s + 1, height s. Plates only touch the cube, never enter it. Same idea builds boxes, lockers, cabinets.
- **Mushroom:** cylinder stem + rounded-cylinder cap.
- **Stepping stone:** one flattened rounded cylinder.
- **Sack:** squashed rounded cylinder + tie + rounded neck. (Currently ≈ 3 tall, over the 2.8 limit; needs shrinking.)
- **Wagon:** one wood tone + dark trim; Inlet bed at 2.5; Weld side boards; corner posts proud; plain cylinder wheels 3 across with hubs (no tyres); 0.5 tongue, 3×0.5×0.5 Weld crossbar, 0.5 stand.
- **Plank pile:** on hold (built from individually rotated pieces).

## Meshes (classic-kit.js MESH)
SpecialMesh children; textures stripped, Part.Color tints them. The preview draws stand-ins. Plants are CanCollide false.
FileMesh size = base × Scale (Part size ignored); scale = wanted size / base. The Head mesh follows Part size × Scale.
- **Fern** `rbxassetid 1091940`: 2 × 3.6 × 2 at scale 3 → base 0.667 × 1.2 × 0.667.
- **Bush** `16659363`: 5 × 2.6 × 5 at 5 → base 1 × 0.52 × 1.
- **Cloud** `1095708`: 5.5³ at 5.5 → base 1.
- **Rounded cylinder:** MeshType 0 (Head), scale 1.25 on a 2 × 1.85 × 2 Part.
- **Spring** `9753878`: base 0.667. **Ring/torus** `3270017`: base 1. **Goblet** `13116112`: base 2. **Book** `1136139`: base 2 × 1.6 × 2. All stretch per axis; use creatively (ring as hoop or rope coil, spring as wire).
- **MeshParts** (Size = rendered size): Teapot 1.969 × 1.55 × 3.148, Kami_Potion 0.95 × 0.95 × 1.521. Both are in the kit catalog; place with `K.mesh`.
- New meshes: ask for an .rbxmx plus one measured size at a known scale.

## Official NDC Build Kit (uploads/fullkit.rbxmx) → `src/fullkit-catalog.json`
The user's source kit; sizes are accurate (MeshParts, Size = rendered size). The catalog lists every item: `{ name, cls, size, color, meshId }` per folder, plus the 32-colour `palette` (`Original_Colors`, classic BrickColors incl. the house colours #f5cd30 / #1b2a35 / #287f47 / #27462d).
- Folders: Animals 18, Containers 27 (potions, buckets, goblet, teapot, mug), Accessories 62 (hats/helmets), Cryptids 6, Explosives 3, Decorations 33 (spring, candle, book, chair, barrel, lampshade, lightbulb, screw…), Scientific 9, Musical 4, Tools 15 (hammer, wrench, torch, broom, tin pot, frying pan…), Holidays 12, Naturals 14 (plant, sprout, bush, rock, sapling, cloud, flame, fire, mushroom), Food 15, Guns 13, Ranged 14, Melee 15, Staffs 12, Parts 21 (classic primitives incl. Cone, Half_Cone, Fourth_Cone, Corner_Cylinder, Bevel_Part, Ring, Seat, Truss), Symbols 8, Alphabet 26, Numbers 10 (1 × 0.4 × 1 decal tiles).
- **Nut / bolt head** (solves bolts with no extra parts): a 1 × 2 × 2 cylinder, `#635f62`, with the "ROBLOX Old Cylinder Icon" decal (`rbxassetid://2674352232`) on both end faces. Kit: `K.nut(group, name, pos, colour, { d, t, rx, ry, rz })`. Bolts are for mechanical builds only (style.md). It's a decal, not a MaterialVariant.
- Use these meshes before inventing props; check the catalog first.
- **Placing a kit mesh:** `K.mesh(group, name, item, pos, colour, { size | scale, rx, ry, rz | R, cc })`, item = a catalog entry (`cat.meshes.Tools.find(o => o.name === 'Torch')`). Writes a real MeshPart (MeshId, InitialSize from the kit, box collision, SmoothPlastic unless `mat`). Sizes stretch per axis freely. Previews draw an ellipsoid stand-in the size of the mesh. Meshes are props: gridCheck and zfight skip them.

## Style references (uploads/)
- `pasted-1791137532225`, `pasted-1791137560338`, `pasted-1791137578032`: 1-stud grid, LEGO-like, stepping, wedges.
- `pasted-1791145670623`: reference campfire (chunky, the fire is the feature).
- `pasted-1791145808416`: execution platform (one-tone deck with Inlet, sparse ground).

## Sandy plateau additions
- **Files:** `plateau-blockout.js` (heights, stairs, paths; `carve` flattens the temple footprint, `extra(K)` hook), `plateau-temple.js` (temple + debris vox), `plateau-dressing.js` (cell-record dressing, palms, plants), `plateau-props.js` (props, vines, moss). Previews `Sandy Plateau {Blockout,Temple,Dressed,Props}.dc.html`, final `Sandy Plateau.dc.html`, export `export/SandPlateau.rbxmx`.
- **Temple recipe:** podium with Inlet top, base course + pilasters 1 proud, flush Inlet panels, 7-rise grand stair with stepped cheeks + 45° wedge caps; columns = 6×6 stone plinth and flared wedge base, FIVE true cylinders (d2) clustered per shaft with cylinder rings, flared capital (collar, hanging wedges, slab, trim abacus); symmetric 45° pediment over the door; one wing intact, one collapsed; sanctum with idol (Head mesh); stone `#d7c59a` + trim `#b9a57a`.
- **Palm generator** (`palmV` in plateau-dressing.js): kinds young / normal / tall / twin, random bend, droop profiles, lean bias, coconuts + crown bud (balls), Weld on bark, Studs on leaf tops, `FK.smooth` + root wedges.
- **Foliage meshes:** Bush and Sprout only (Plant and Sapling look wrong in Roblox). Height check wants 1–4.
- **Vines, not roots:** leaf greens `#4a7a3b` `#3d6a35` (some Studs) spiralling up columns, climbing walls. No brown wood roots (brown isn't used elsewhere).
- **Pebbles:** flat cylinder discs, diameter 1–3, 1 thick, no tilt, flush on whole stud cells, never tilted or random-sized.
- **Kit-mesh props used:** Vase, Ceramic_Potion, Bowl, Goblet, Bag, Book (tablet stacks), Candle, Apple, Broom, Mushroom, Symbol_* (carved marks, flat `rx 90`), Ring. Terracotta `#a65f45` for pots.
- **Bowl mesh imports UPSIDE-DOWN in Roblox:** place with `rx 180`; the preview stand-in is drawn inverted to match. Check other meshes' orientation with the user before relying on them. Don't put primitive fills (grain, sand) inside bowl meshes.
- **User's meshes:** `uploads/tikihead.rbxm` = MeshPart `rbxassetid://11114452856`, InitialSize 16.09×35.5×16.59, placed at 4.76×10.5×4.91 (the toppled head, face assumed −Z).
- **Rejected in this set:** rope coil and a mesh brazier bowl (mesh orientation), cloned palms, grain discs in bowls, tilted/random pebbles, brown roots.

## Overlap rule for props (user: "not a single clipping part")
No crate or barrel part may share volume with ANY other part, including neighbouring props, the wagon and each other. A single crate or barrel is built clean; the clipping comes from layouts. Rotated props need a footprint check: a crate is s+1 wide with its side plates (s+0.5 for s < 2 front/back only), a big barrel hoop is 3.5 wide. Use the SAT overlap check (OBB vs OBB, penetration > 0.02 = clip) over every Part box; tools.md has the recipe.

## Crates and barrels: primitive versions SCRAPPED (user, quarry session). The kit has a Barrel mesh: USE IT (Decorations/Barrel 2.33×3.16×2.29).
Our block-built crate and barrel did not read (the small barrel had too little belly to register as a barrel). Removed from the quarry, tent, campfires, wagon and classic test. The user will make their own versions or find meshes; use those when supplied and do not rebuild them from primitives. `classic-kit.js` still exports the old `crate`/`barrel` and `Crate and Barrel.dc.html` still shows them, as a record only.

## Snow pine generator (`snow-pines.js`, approved)
4×4 trunk to 6 then 2×2 (Weld splotches, root wedges); whorls every 3 studs (cardinal and diagonal whorls alternate, 12% dropouts), bough length follows a cone (min 2), droop 0.5→0.2, centre line + stepped lateral fans (half-width ≤ 2) + dark under-layer. Foliage greens `#33503f` (centre), `#345141` (fans), `#2a4535` (under); snow `#f1f5f8` (30% Studs) on ~75% of exposed centre tops and ~30% of fan tops. Spire = green 1×1, 3 tall, snow cap. Kinds: big ht 34 R 8 y0 10, mid ht 26 R 6 y0 8, small ht 20 R 4 y0 7. Foliage floor = ground + 7.
Snow terrain: Studs snow cap plates (0.2) on plain body boxes, 2 tones (darker on ~10% in stamped rects), packed-snow paths `#c3ccd4`, Inlet ice `#a9cde0`/`#9bbfd4`, snow-capped rock-pile props, raised 0.5 Studs drifts, rock `#8d9096`/`#7e8187`.
