# Development Roadmap

Phases follow the master brief. Each phase has objectives, tests, completion criteria. Work incrementally — show results throughout, don't hide progress until phase end.

## Phase 0 — Project Inspection and Foundation  ⟵ CURRENT
- [x] Inspect Roblox place, Blender, Obsidian
- [x] Identify accessible tools
- [x] Preserve/wipe per user decision
- [x] Establish naming conventions
- [ ] Establish coordinate system + half-scale target
- [x] Create core project notes
- [x] Document current implementation
**Done when:** project understood, memory in place, next task identified.

## Phase 1 — Ragnarok Research and Map Blockout
- Research map references, determine target dimensions
- Define coordinate conversion
- Create rough geographical blockout, major regions, landmark markers
- Record uncertainties; present blockout for inspection
**Done when:** layout + scale reviewable before detailed production.

## Phase 2 — First High-Quality Environment
- Pick one representative region; terrain, elevation, custom Blender assets, vegetation, rocks, a landmark, lighting, traversal, collision/performance test
**Done when:** region shows target art quality and pipeline works.

## Phase 3 — Character, HUD, Basic Survival
- Spawning/respawning, R6+R15, survival HUD, health/stamina/food/water, gathering, inventory, hotbar
**Done when:** player can enter, survive, gather, use HUD/inventory.

## Phase 4 — Survivor Character Creator
- Creation UI, 3D preview, appearance presets, skin tone + controls, randomize/reset, validation, R6+R15, save/restore
**Done when:** customize, enter, rejoin, appearance persists.

## Phase 5 — Inventory, Crafting, Building
- Item defs, recipes, tools, placement preview, snapping, ownership, server validation, save/load
**Done when:** gather, craft, equip, build reliably.

## Phase 6 — Tribe System
- Data structures, creation, management UI, invites, roster, roles/permissions, promote/demote, kick/leave, leadership transfer, disband, integrate with buildings + creatures, notifications, multi-client tests
**Done when:** create/manage tribe, invite/remove, control shared assets securely.

## Phase 7 — Creatures and Taming
- Creature framework, first detailed model, movement/AI, health/combat, taming, interactions, ownership integration, performance/nav tests
**Done when:** at least one complete creature encounterable + manageable.

## Phase 8 — Menus and Server Management
- Loading screen, main menu, character creation hookup, solo, private/friends, server browser, join behavior, errors, settings
**Done when:** game modes work through the UI, not decorative buttons.

## Phase 9 — Expand the Map
- Complete regions one by one, improve accuracy, landmarks, assets, caves, resources, habitats, transitions, scale/streaming, docs
**Done when:** each region meets standard, full layout coherent.

## Phase 10 — Persistence and Multiplayer Integration
- Player/tribe/creature/structure persistence, validation, concurrency, disconnect/rejoin, shared world state, permissions under multiplayer
**Done when:** state persists reliably, multiplayer follows rules.

## Phase 11 — Polish and Release Prep
- Refine models/materials/lighting/audio/animations/UI, optimize, test R6+R15, solo+multiplayer, persistence, bugs, docs, release checklist
**Done when:** loop testable, systems work together, critical issues addressed.
