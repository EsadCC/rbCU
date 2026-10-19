# ARK Visual and Gameplay Reference

*Researched 2026-10-16. Visual reference only: create original Roblox assets and interface elements; do not reuse ARK logos, screenshots, meshes, textures, sounds, or video in the shipped game.*

## Reference screenshots supplied by the user

The attached images are the primary target for UI structure and visual language.

- **Inventory / survivor**: left inventory grid and search/sort controls; center survivor name, level, location, day/time/weather, XP and upgradeable stats; right equipment and large 3D survivor preview; hotbar stays visible at the bottom.
- **Crafting / engrams**: categorized item grid with unlock level/point cost, search/filtering, selected recipe details and required materials; keep the world visible behind the translucent panel.
- **Character creation**: body-region sections with grouped sliders on the left; real-time 3D survivor preview in the middle; spawn region and survivor naming on the right.
- **Options**: multi-column dense settings with category navigation, icon tabs, sliders/toggles/dropdowns and Apply/Save/back controls; preserve the scene behind the panel.
- **Session list**: large table with server name, map, player count, ping, day, mode, build/mod status; top filters for name/map/mode/sort; bottom toggles and join/refresh/favorite/cancel actions.
- **Main menu**: dark cinematic background; one large original emblem/title; compact vertical menu around the center/lower center; patch/update information and secondary details in the margins. Do not copy ARK's triangular logo.
- **Gameplay HUD**: keep the world unobstructed. Put a ten-slot hotbar at bottom center, survival state icons down the right, actionable prompts and item notices near edges, and optional extended day/time/location/temperature details.
- **Engrams / crafting**: dense but legible icon tiles with clear unlock/progress state and an adjacent recipe/material inspector.
- **Gameplay images**: beaches, rivers, forest edges, cliffs, ruins, caves, snow and volcano should feel like distinct places, not a blank flat plane.

## Visual system to carry into the project

- Full-screen game background remains visible through large dark blue/teal translucent panels.
- Thin bright cyan edges, angular corner cuts, hexagon pattern behind panels, cyan headings/icons, cool light body text, restrained amber for warnings/highlights.
- Strong condensed uppercase screen titles, compact readable labels, icon-led controls, consistent spacing, highlighted/hover/selected/disabled states.
- Prefer full-screen multi-panel layouts over small generic centered cards for inventory, character creation, options and server browser.
- Show real 3D models in ViewportFrames for the survivor and equipment when available; show original item illustrations/thumbnails. Use authored project art only.
- Preserve controller/touch usability: larger hit areas and responsive panel sizing, even when the desktop layout is dense.

## ARK gameplay systems to account for in UI

1. **Spawn and survival**: choose a spawn region; monitor health, stamina, oxygen, food, water, weight, temperature, torpor and contextual effects.
2. **Gathering**: collect resources from world nodes; show gain/drop notices and inventory totals.
3. **Inventory and equipment**: search/sort/filter item stacks, inspect item details, equip gear and assign items to hotbar slots.
4. **Crafting and engrams**: browse learned recipes, unlock progress, required materials, craft queue and results.
5. **Progression**: XP/level, available points, survivor stats and unlockable recipes.
6. **Creatures**: encounter, fight, knock out, feed/tame, monitor taming progress and creature stats/inventory.
7. **Building**: select structure pieces, show placement preview, snap/validity feedback, repair/demolish and ownership.
8. **Tribes**: members, ranks/permissions, invites, shared structures and tames.
9. **Exploration**: map/regions, day/time, temperature/weather, landmarks, caves/dungeons and discovery notes.
10. **Servers**: filter/map/mode/search, players/ping/day/build, favorite/refresh/join and explicit local/host status.
11. **Options**: audio, graphics, gameplay, camera, accessibility and general UI scale with Apply/Save feedback.

## Source links

### Primary gameplay and UI references
- [ARK Official Community Wiki — HUD](https://ark.wiki.gg/wiki/HUD)
- [ARK Official Community Wiki — Inventory](https://ark.wiki.gg/wiki/Inventory)
- [ARK Official Community Wiki — Options](https://ark.wiki.gg/wiki/Options)
- [ARK Official Community Wiki — Server Browser](https://ark.wiki.gg/wiki/Server_Browser)
- [ARK Official Community Wiki — Getting Started](https://ark.wiki.gg/wiki/Getting_Started)
- [ARK Official Community Wiki — Crafting](https://ark.wiki.gg/wiki/Craft)
- [ARK Official Community Wiki — Engrams](https://ark.wiki.gg/wiki/Engrams)
- [ARK Official Community Wiki — Tribes](https://ark.wiki.gg/wiki/Tribes)
- [ARK Official Community Wiki — Ragnarok](https://ark.wiki.gg/wiki/ARK%3A_Ragnarok)
- [ARK Official Community Wiki — Biomes](https://ark.wiki.gg/wiki/Biomes)
- [ARK Official Community Wiki — Caves](https://ark.wiki.gg/wiki/Caves)
- [ARK Official Community Wiki — Controls](https://ark.wiki.gg/wiki/Keys)
- User-provided screenshots attached in this task; use these for interface composition and interaction details.

### Images for offline visual study (external examples; not game assets)
![ARK survivor customization example](https://www.supersoluce.com/sites/default/files/node/69492/ark-survival-evolved-guide-complet-creation-du-personnage-002.jpg)
[Source page — character creation reference](https://www.supersoluce.com/soluce/ark-survival-evolved/creation-du-personnage?support=ps4)

![ARK inventory and survivor stats example](https://images.steamusercontent.com/ugc/454118974115344985/3444CBC9C51C121C5F0AD98979FB4074EDBD6B9C/?ima=fit&imcolor=%23000000&imh=576&impolicy=Letterbox&imw=1024&letterbox=true)
[Source page — inventory screenshot](https://steamcommunity.com/sharedfiles/filedetails/?id=722244725)

![ARK server browser example](https://www.ionos.mx/digitalguide/fileadmin/DigitalGuide/Screenshots_2021/ark-survival-evolved-server-list.jpg)
[Source page — session list screenshot](https://www.ionos.mx/digitalguide/servidores/know-how/ark-crear-un-servidor-dedicado/)

### Video
[Official ARK: Survival Evolved — Ragnarok trailer (YouTube)](https://www.youtube.com/watch?v=NfaOogXlG3g)

## Current project audit
The attached ARK screenshots show the desired structure and density. The current Roblox place does not yet have equivalent inventory, creator, options, server-list or tribe screens. In Studio, the world currently appears as a mostly empty baseplate; `ReplicatedStorage.HeroDiorama` exists, but its mesh surfaces render as checker-like placeholders. Do not treat the diorama as final menu art. Build out the world and authored art before using it as a cinematic background.
