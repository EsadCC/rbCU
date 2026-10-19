# Decision Log

Chronological record of important decisions and why they were made.

---

## 2026-10-16 — Wipe the existing project
**Decision:** Delete the entire "Cursed Ride Builder v7" project (22 instances: scripts, GUIs, modules, remotes, folders, baseplate) from placeId 99057849884548 and build ARK in the same place.

**Reason:** The existing project was a finished game of an unrelated genre (obstacle/vehicle run builder). The ARK brief and the existing project are mutually incompatible in one place.

**Alternatives considered:** Building ARK in a separate new place (rejected by user — they wanted this place reused).

**Consequences:** Old work is gone, unrecoverable. Nothing in this vault documented it, so no notes are affected. Fresh start.

**Approved by:** User (explicit).

---

## 2026-10-16 — Half-scale map
**Decision:** Target ~50% of Ragnarok's original width and length (≈25% land area) as the initial map size.

**Reason:** User's brief specifies it. Keeps exploration practical and development scope manageable on Roblox while preserving recognizable geography.

**Note:** Player size, creatures, buildings stay full-scale for believable gameplay. Only the map layout is halved.

**Approved by:** User (in brief).

---

## 2026-10-16 — Folder architecture
**Decision:** Created the proposed folder structure from the brief (Shared/Remotes/Assets in ReplicatedStorage; Bootstrap/Services in ServerScriptService; template folders in ServerStorage; UI folders in StarterGui; World/Regions/etc in Workspace).

**Reason:** Matches the brief's starting proposal and gives scripts a consistent home.

**Status:** Empty folders only — no scripts placed yet. Structure may evolve.
