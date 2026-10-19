---
tags: [roblox, map-building, rules]
type: rules
---
# Build Rules

Back to [[Roblox Dev Resources]] | Used with: [[Prompt - Map Building]]

## Non-negotiable for every map change

- **Static Parts only.** Builds are placed once and saved in Workspace; no generator scripts are left in the game.
- **Zero Z-fighting:** no coplanar overlapping same-facing faces. Layered details protrude by ≥ 0.1 studs.
- **Zero floating parts:** everything rests on, or attaches to, something.
- No Roblox Terrain. No StreamingMesh LOD.
- Detailed, recognizable props; never plain coloured blocks.
- Real interiors, no fake doors or pointless rooms. Give players alternate routes, back doors, balconies and shortcuts.
- Lived-in detail (signs, clutter, wear) without overfilling.
- New lights get the `CullLight` tag. Foliage has collision off. Parts under 1.5 studs have collision off.
- Wrap Studio edits in ChangeHistory recordings.
- After a build, run **ZF** until 0, then **FL** until 0. Then test routes with pathfinding (agent radius 1, no jump).
- Back up replaced models to `ServerStorage._MapBackups`.

## Walkability gotchas

- Stairs steeper than ~40°, or with less than ~3 studs of space at the foot, fail pathfinding.
- Doorways need ≥ 2.8 studs clear and balconies ≥ 3.5.
- Check headroom over stairwells (a roof cap plate once blocked one).
