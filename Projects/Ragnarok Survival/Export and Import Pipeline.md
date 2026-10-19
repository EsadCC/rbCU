# Export and Import Pipeline

## The problem
Blender on this machine **hard-crashes on any render or screenshot** (bpy.ops.render.render, render.opengl, get_viewport_screenshot all fail with WinError 10054). Geometry building, saving, and FBX export work fine. Also, the Roblox MCP bridge has **no command to import a local FBX**.

## The solution (WORKING)
A geometry-transfer pipeline that bypasses both problems:

1. **Blender** builds the mesh, then dumps its geometry to JSON:
   - `verts`: list of [x,y,z] (Blender Z-up, deduped)
   - `tris`: list of [i,j,k] **0-based** indices
   - Written to `Obsidian Vault/Projects/Ragnarok Survival/_geom/<Name>.json`
   - Multi-material objects dump one group per material (trunk/leaf split).

2. **Blender serves the files** over local HTTP:
   - Python `http.server` in a daemon thread, port **8090**, dir = `_geom`
   - Started via `execute_blender_code`. **Lost if Blender restarts** — must restart.

3. **Roblox** fetches and rebuilds:
   - `HttpService:GetAsync("http://127.0.0.1:8090/<Name>.json")`
   - `AssetService:CreateEditableMesh()` → `AddVertex` → `AddTriangle`
   - `AssetService:CreateMeshPartAsync(Content.fromObject(em))`
   - **Coordinate conversion:** Roblox vertex = `(x, z, -y)`. Blender triangle index `i` → Lua `map[i-1]` (0-based fix).

## Why this works
- No render needed (avoids the crash).
- No FBX import dialog needed (bridge can't do it anyway).
- Verified in the real target engine (Roblox), which is what matters.
- EditableMesh test confirmed: CreateEditableMesh / AddVertex / AddTriangle / CreateMeshPartAsync all OK.

## Requirements
- Roblox `HttpService.HttpEnabled = true`
- Blender HTTP server running on 8090

## Known limits
- Geometry only — no baked textures; materials are assigned as Roblox Material + Color per group.
- Re-dumping requires re-running the Blender dump script for the changed assets.
