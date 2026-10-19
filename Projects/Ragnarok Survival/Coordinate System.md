# Coordinate System

One consistent convention across Blender and Roblox. Use everywhere.

## Axis conventions
| | Blender | Roblox |
|---|---|---|
| Forward | -Y | -Z (look vector) |
| Up | +Z | +Y |
| Right | +X | +X |

**Conversion Blender → Roblox:** rotate -90° about X. In Blender export, set forward = -Z, up = +Y (glTF default handles this).

## Unit conversion
- Roblox: 1 stud. 1 stud ≈ 0.28 m real-world.
- Blender: work in meters, 1 Blender unit = 1 m.
- **1 m = ~3.57 studs.** Use 3.57 as the conversion factor, or simply build to Roblox scale directly and check size in Studio.
- **Practical rule:** build assets at final Roblox stud size. Don't rely on a scale factor at export — verify dimensions after import.

## World origin
- Origin (0,0,0) = center of the playable map, at sea level (Y=0).
- Terrain water at Y = 0, land rises above.

## Roblox terrain limits
- Terrain MaxExtents observed: ±32000 studs (64,000 across).
- Target map must sit comfortably inside this.

## Scale factor
- Half-scale Ragnarok: see [[Map Scale]].

## Region grid
- Divide the map into a grid of named regions (e.g. 4×4) for streaming and organization.
- Boundaries to be set once blockout dimensions are fixed.

## Landmark coordinates
*(populated as blockout proceeds)*

## Elevation
- Sea level: Y = 0
- Beach: Y ≈ 0–8
- Plains/forest: Y ≈ 8–120
- Hills: Y ≈ 120–400
- Mountains: Y ≈ 400–1200 (half-scale; original peaks are far taller)
- Snow line: ~Y 500+

*Values are provisional — refine after blockout.*

## Uncertainties
- Exact original Ragnarok dimensions NOT yet verified from a primary source. See [[Map Scale]].
