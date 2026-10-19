# UI System

*Updated: 2026-10-16 (ARK reference pass)*

## Visual direction
Use the user-provided ARK screenshots as layout and interaction references: dark teal translucent full-screen panels over visible gameplay, thin cyan borders, angular/hex details, condensed uppercase headings, dense but legible grids, and a 3D survivor preview. The game must use original Roblox art and branding. Do not ship ARK logos, screenshots, models, textures, sounds, or video.

## Implemented in Roblox Studio
- Loading screen uses the existing diorama in a ViewportFrame with a runtime camera; progress is staged presentation, not measured streaming.
- Main menu uses an original three-shard artifact in a ViewportFrame, title, vertical navigation and an information panel. Survivor/Settings remain limited panels.
- Inventory uses a three-column layout: item grid and search/filter controls; survivor stats and detail area; live 3D avatar preview. I opens inventory and V opens crafting view. Item stacks come from server snapshots and update events. Craft requests use the existing service.
- Server inventory publishes read-only snapshots and change events. Player/data/survival initialization handles both new joins and players already present when services start.
- HUD uses right-side compact survival icons, ten-slot bottom hotbar, region text, and event-driven gather/craft notices. H toggles extended values; number keys select hotbar slots.
- Visual/gameplay research board: [[ARK Visual and Gameplay Reference]].

## Verification
- Play mode confirmed replacement Loading, Menu, Inventory and Survival HUD controllers started without project-script errors in inspected output.
- Inventory RemoteFunction returned an empty snapshot when empty; a temporary server-side item grant produced wood/stone/fiber counts and corresponding visible grid entries. Test items were cleared before stopping.
- Captured Play HUD: right-side meters and centered hotbar rendered. Notice event was fired, but the toast did not appear in the later capture; toast visibility still needs a focused verification.
- Inventory/avatar and title screens were captured during this pass; see current screenshots in task history.
- Stopped Studio Play and returned to Edit mode.

## Known gaps
The options, character creator, server browser, tribes, map, engram unlocks, creature/tame, building and full settings screens are not implemented as complete screens. Weight, leveling and equipped item state are not fully connected. The live world currently appears mostly as a flat baseplate with a spawn pad and sparse distant props. ReplicatedStorage.HeroDiorama meshes render checker-like placeholders; do not use them as final scenic art. Older vault notes describing a fully built terrain/biome scene are stale or unverified against the current live place.

## Next
Build authored playable world scenery and original creature/item art, then continue with the full character creator and options/server screens. Keep the live game visible behind large translucent panels.
