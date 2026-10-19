# Project Overview

## What this is
A Roblox survival game inspired by ARK: Survival Evolved, specifically the **Ragnarok** map. Not a generic dinosaur game — the goal is to reproduce the ARK experience (survival loop, character customization, HUD, inventory, crafting, building, tribes, creatures/taming, multiplayer) as faithfully as technically practical on Roblox.

## Core pillars
1. **Ragnarok geography** — recognizable layout at ~half the original width/length.
2. **Detailed original 3D models** — Blender-produced, not default Roblox parts.
3. **Complete survival gameplay loop** — see roadmap phases.
4. **R6 + R15 support** — both rigs tested throughout, not bolted on at the end.
5. **Obsidian memory** — this vault is the persistent brain across sessions.
6. **Incremental development** — small, testable, visible steps.
7. **Honest progress** — a feature is only "done" after testing.

## Tooling
| Tool | Role | Connection |
|------|------|-----------|
| Roblox Studio | Game engine, world, scripts, UI | ZeroScript MCP bridge (28 commands) |
| Blender | Custom 3D assets | blendmcp bridge, port 9876 (29 commands) |
| Obsidian | Permanent project memory | file MCP (this vault) |

## Place identity
- placeId: 99057849884548
- Previous contents: "Cursed Ride Builder v7" — **wiped on 2026-10-16** at user request.
- Intended name: **Ark Ragnarok** (must be set in Studio UI; game.Name is read-only from Luau).

## Important constraint
ARK is a **visual and gameplay reference only**. Do NOT reuse ARK's proprietary models, textures, audio, or data files. All assets original or appropriately licensed.
