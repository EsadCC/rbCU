# Current State

*Last updated: 2026-10-16 (ARK reference and UI pass)*

## Phase
Survival project with a verified first pass of reference-led UI. Older session notes document broader systems, but verify those claims against the live place before relying on them.

## Current UI state
- Original dark title screen with geometric artifact, vertical actions and supporting info panel.
- Three-column Inventory screen with server-fed item stacks, survival values, item details and live avatar preview.
- Compact right-side HUD survival icons and ten-slot centered hotbar.
- Inventory opened with I; crafting view with V; H shows extended HUD values; number keys select hotbar slots.
- [[UI System]] records details and known gaps. [[ARK Visual and Gameplay Reference]] collects the screenshot spec, sources, system map, external image examples and official trailer.

## Verification
Play mode on 2026-10-16 started the replacement Loading, Menu, Inventory and Survival HUD controllers. Inventory snapshot path returned zero items when empty; temporary server-granted materials appeared as three inventory cards, then were cleared. HUD icons and hotbar rendered. The notification event was fired but its toast was not visible in the later capture; recheck.

Studio is back in Edit mode.

## Live world audit
The live Play capture shows a mostly flat baseplate, one spawn pad and sparse distant props, not the terrain/biome scene described in older notes. ReplicatedStorage.HeroDiorama exists but its mesh faces render checker-like placeholders. Treat older detailed terrain/object counts as stale or unverified. The current UI is not yet backed by a finished scenic environment.

## Not complete
Full character creation, options, server browser, tribes, map, engram unlock flow, building, tame management, and a finished authored world remain outstanding. Current inventory UI does not implement full weight, level progression or equipment state.
