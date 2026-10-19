# Architecture

Server-authoritative, modular Luau. All gameplay logic on the server; clients handle input + UI.

## Folder layout
```
ReplicatedStorage/
  Shared/
    Config/SurvivalConfig (ModuleScript)
    DataDefinitions/ItemDefs (ModuleScript)
    Types/  Utilities/
  Remotes/
    StatsUpdate, StatChanged, Notification, RequestAction
  Assets/

ServerScriptService/
  Bootstrap/Bootstrap (Script) — starts services
  Services/
    InventoryService (ModuleScript)
    SurvivalService (ModuleScript)
    GatheringService (ModuleScript)

StarterGui/
  HUD/SurvivalHUD (ScreenGui, disabled by default)

StarterPlayer/StarterPlayerScripts/
  SurvivalHUDController (LocalScript)
  GatherController (LocalScript)

Workspace/World/
  RockLibrary, TreeLibrary, VegetationLibrary, StructureLibrary,
  ResourceNodes, Scatter (1,333 placed), Regions, Runtime
```

## Remotes
| Name | Direction | Purpose |
|------|-----------|---------|
| StatsUpdate | S→C | full stat table, 4/sec |
| Notification | S→C | event messages (gathered, etc.) |
| RequestAction | C→S | client actions: "sprint", "gather" |

## Service contract
Every service module must export a `Start()` function. Bootstrap calls them in order:
1. InventoryService (no-op Start)
2. SurvivalService
3. GatheringService

## Server authority
- Stats (health/stamina/food/water) computed + stored server-side.
- Inventory stored server-side; clients never set counts.
- Gathering validates: node is tagged, player within 16 studs, rate-limited 0.4s.
- Sprint is a client hint but stamina drains server-side.

## Item system
Data-driven via `ItemDefs`. Adding an item = adding one table entry. Node yields in `ItemDefs._yields` keyed by node type.
