# Known Issues

Active problems, ordered by severity.

---

## Blockers
*(none)*

## Bugs
*(none — no gameplay code exists yet)*

## Limitations / environment
- **Place rename requires manual action.** `game.Name` is read-only from Luau. The user must rename "Untitled Experience" → "Ark Ragnarok" via File → Game Settings in Studio.
- **execute_luau Edit-mode only when playing.** In Play mode, use `###LUA:Server###` or `###LUA:Client###`.
- **Terrain is currently the default empty 64k-stud grid.** No world geometry yet.

## Technical debt
- Folder architecture created as empty containers ahead of the scripts that will fill them. Expect adjustment once real systems land.

## To verify later
- Blender → Roblox export pipeline (FBX/OBJ import, scale, materials) not yet exercised end-to-end.
