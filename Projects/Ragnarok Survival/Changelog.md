# Changelog

Reverse-chronological. Only verified changes.

---

## 2026-10-16 — UI pass

### Added
- Rebuilt loading and main menu layouts with an original dark teal/cyan survival-game visual direction.
- Added runtime camera setup and hero diorama framing to the loading viewport; this fixes the previous missing-camera black background.
- Added menu navigation, honest in-development Survivor panel, and local scale control in Settings.
- Added replacement HUD controller with recursive bar lookup and ten-slot selection styling.
- Added [[UI System]] implementation and known gaps.

### Fixed
- Main menu information overlay lookup now follows its actual ScreenGui hierarchy.
- Disabled the three superseded UI controllers to prevent duplicate connections.

### Verified
- Play mode startup; ArkLoadingController, ArkMenuController, and ArkSurvivalHUDController printed ready.
- HUD found four stat bars; main menu rendered in Studio.
- Full server-side payload/action behavior for HUD stats and hotbar remains unverified.

---

## 2026-10-16 — Session 2 (long autonomous run)

### Added
- **Asset pipeline** (Blender→JSON→HTTP:8090→Roblox EditableMesh).
- **43+ Blender assets**: 13 rocks, 6 trees, 12 vegetation/props, 9 structures, 4 ore nodes.
- **2 creatures**: Dodo, Raptor (built, imported).
- **Real terrain** across all biomes + 620-stud peak + ocean ring.
- **1,333 scattered objects**.
- **Survival loop**: HUD (health/stamina/food/water), decay, starve damage, sprint.
- **Gathering**: 1,244 tagged nodes, click-to-harvest, item drops.
- **Inventory**: server-authoritative.
- **Crafting**: recipe system.
- **Creature system**: spawn regions, AI (idle/wander/chase/flee), combat, drops, respawn, 24 spawns.
- **Player combat**: melee.
- **Taming system**: feed-to-tame, follow owner.
- **DataService**: DataStore persistence (inventory), autosave, BindToClose.
- **Main menu**: title screen + Play/Character/Settings + MenuController.

### Fixed
- Creatures fell through world (unanchored) → anchored.
- CanQuery=false broke click targeting → true.
- Luau reserved word `in` in RecipeDefs/CraftingService → renamed to `ingredients`.
- Removed Gemini's post-processing effects (Sky/SunRays/DoF/Bloom) causing white-washout.

### Verified
- All 8 services + 4 client controllers start clean in Play.
- 24 creatures spawn, wander, chase, flee, damageable.
- DataStore enabled and loading/saving.

### Blocked
- **Blender offline** (bridge :9876 + geom server :8090 dead) — needs manual reconnect for more creature models.

## 2026-10-16 — ARK visual reference and UI pass

### Added
- [[ARK Visual and Gameplay Reference]] with the user's screenshots as the primary composition spec, focused wiki references, external image study examples and official Ragnarok trailer.
- Three-column inventory screen, server-published inventory snapshot/change path and live avatar ViewportFrame.
- Compact icon-based HUD with centered ten-slot hotbar, extended stats toggle and gather/craft notice listener.
- Original three-shard menu emblem and vertical navigation.

### Fixed
- Inventory and survival initialization now covers both players already online at service start and later joins.
- Removed the unsupported hotbar remote action; selection is handled by the client UI.

### Verified
- Play-mode controllers started; inventory snapshots and temporary item update populated visible resource cards. Temporary test items were cleared.
- HUD meters and hotbar rendered in Play. Gather notice event fired, but toast visibility was not confirmed in capture.
- Live world audit contradicts older detailed-terrain claims: scene currently appears as a sparse baseplate; HeroDiorama meshes show checker-like placeholders.
- Returned Studio to Edit mode.
