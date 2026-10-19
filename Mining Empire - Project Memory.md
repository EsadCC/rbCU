# Mining Empire — Project Memory

Roblox mining simulator. Player mines ores, collects, sells, and recruits miners that auto-mine for passive income.

**Place:** theking34tr's Place (placeId 90996133502092)

---

## Where things live

### ReplicatedStorage
- `Shared` — `Config` (ALL game data/formulas), `Format`, `ClientState`, `SFX`, `UpgradeDefs`, `UIKit`
- `Net` — `State`, `Notify`, `OpenPanel`, `NodeHit`, `Popup`, `MineSwing` (RemoteEvents), `Request` (RemoteFunction), `RollAnim`
- `Icons` — `Miner` (per rarity), `Ore` (per ore), `UI` (Book, Dice, Compass, MoneyBag, House, Backpack, Clover, Forge, Chest, Monument, Pickaxe, Crates, Cart, Pick_Stone)

### ServerScriptService
- `Modules` — Shop, Miners, Plots, Sync, Economy, Rolls, PlayerData, Nodes, Tools, OfferStore
- Scripts — PlayerLifecycle, NodeSpawner, MiningHandler, MinerLoop, RequestHandler, AutoSave, SellMarket, Leaderboards, _DebugCheat, Stations

### StarterPlayerScripts
MineClient, VisitUI, MinerAnimator, ShopUI, IndexUI, UpgradeBoards, SellBoard, BiomeAmbience, HUD, InventoryUI, RollUI

### Workspace
- `Plots.Plot1..6` — each has Floors, Stations (SellStation / StorageStation / RecruitStation), Slots, Decor, Podiums, Nodes, Miners, NameplateAnchor, MineSign, PlotSpawn, Lodge
- `Hub` — leaderboards, HubSpawn

---

## Conventions

- **All UI actions** go through ONE RemoteFunction `Net.Request` with `(action, payload)`. Add server handling in `RequestHandler`.
- Client reads state via `Shared.ClientState` (State remote + Changed event + Request helper).
- **All numbers/formulas** live in `Shared.Config`. Rarity order: Common, Uncommon, Rare, Epic, Legendary, Mythic, Secret.
- HUD/UI built with `Shared.UIKit` helpers (`UIKit.New`, `UIKit.Text`, `UIKit.Button`, `UIKit.Icon`, `UIKit.Icon3D`, `UIKit.MakePanel`, `UIKit.Toast`, `UIKit.Colors` as `C`).
- Stats stored in PlayerData session table; saved via DataStore `MiningEmpire_v1`.

---

## Key systems

- **Plots** — 6 plots, open to everybody. Nameplate shows owner avatar + name + income; unowned shows NOTHING (the old "Free Plot N" text was removed). NameplateAnchor raised to Y=190.
- **Rolls** — roll is FREE, produces offers shown on podiums (up to rollcap, max 6). Offers bought with cash. `Rolls.Roll` fires the `RollAnim` remote for the client animation.
- **Cave / lodge** — 3 slots per level, 10 levels (3 → 30). `Config.CaveCost`, `Config.CaveNames`, `Config.CaveLevel`.
- **Collection multiplier** (in `Config.CollectionMult`) — +0.10x per 5 miners, +0.05x per 5 ores, +0.10x per 5 mutations.
- **Selling + collecting** are ProximityPrompt-based (`Stations` script), NOT auto-on-proximity.
- **Leaderboards** refresh every 30s.

---

## Decisions & gotchas

- **Rebirths fully removed:** `Shop.Rebirth`, the `"Rebirth"` action in RequestHandler, and the rebirth fields in `Sync`. (`Config.RebirthCost` / `RebirthMult` still exist but are unused.)
- Never build at world center in a plot without checking bounds — Build Rules: zero floating parts, zero Z-fighting.
- `ShopUI` line ~45 (`col:Lerp(...)`) throws `attempt to index nil with 'Lerp'` — `catColor[def.cat]` can be nil for some upgrade categories. Needs fixing.

---

## User preferences

- Hates plain/lame UIs. Wants **colorful, blocky Roblox-style** UIs with icons (Blox Fruits / pet-sim style).
- Wants custom SFX, not default sounds.
- Wants UIs **smaller** (they currently overlap).
- Wants money **bottom-left**, a nice inventory UI at the bottom, and miners accessed via an inventory icon (not a tab).
- Wants changes made **one at a time**, small steps, visible progress.

---

## Open questions / TODO

- Roll animation: black out all miners first, reveal on animation end.
- Miners should spin slowly when clicking UI; custom pickaxes for miners.
- Miner work station / cave: a separate spot miners emerge from and return into.
- More slots (30 max), starting at 1 podium then growing.
- Fix `ShopUI` `catColor` nil error.

---

## Related notes

- [[Check UI Clean (Roblox) - Setup Guide]]
