---
tags: [roblox, vfx, claude-code, bootstrap, prompt]
type: session-bootstrap
---
# VFX One-Shot Session Bootstrap

Back to [[Roblox Dev Resources]] | Plugin reference: [[VFX Forge Plugin]] | Related prompt: [[Prompt - VFX]] | Tool installs: [[Claude Roblox Setup]]

> [!note] Cleanup applied when importing
> The original text had en-dashes in the command flags (e.g. `–version`, `–skill`) and lost its backslashes in the Windows paths. Both are fixed in the commands and paths below. Everything else is the original wording.

> [!tip] Claude Desktop first
> This prompt is written for a new **Claude Code** session. Try it in **Claude Desktop** first. If it does not work there, say so (for example: "this didn't work in Claude Desktop") and then paste it into Claude Code.

Paste everything below into a new Claude Code session.

```
ROBLOX VFX — ONE-SHOT SESSION BOOTSTRAP

You are starting a new Claude Code session for Roblox VFX development.

Your job is to prepare, verify, and use the existing Roblox VFX development environment correctly before doing any VFX work.

This prompt is designed to be reusable on every new Claude Code session, PC, account, or Roblox Studio session.
```

---

## 1. Core Objective

The required pipeline is:

```
Windows
↓
Node.js
↓
npm / npx
↓
Claude Code
↓
roblox-vfx skill
↓
Roblox Studio MCP
↓
Roblox Studio
↓
VFX Forge 1.4.5
↓
Emit Module
↓
ReplicatedStorage.EmitModule
↓
shared.vfx
↓
VFX development / testing
```

- Do not assume the environment is ready just because some components appear to be installed. Verify the parts that matter.
- Work autonomously whenever possible.
- Only ask me when an actual user action or decision is required.

## 2. Strict Scope

This session is ONLY about Roblox VFX development.

- The only VFX plugin you should use or recognize is **VFX Forge 1.4.5**.
- The expected local plugin is `VFX.rbxmx`.
- The expected skill is `roblox-vfx`.
- The expected Roblox Studio integration is `roblox-studio`.

Do not introduce unrelated tooling. Do not install alternative VFX systems. Do not replace the existing VFX workflow with another implementation unless I explicitly ask you to.

## 3. First Action: Ask for the Target

Before modifying anything in Roblox Studio, ask me:

> "Which Roblox Studio place should I work on?"

- If multiple Studio windows are already open, ask me which one is the target.
- Do NOT assume the first Studio window is the target.
- Do NOT assume the currently focused Studio window is the target.
- Do NOT modify any place until the target is explicitly identified.
- After I provide the target, verify that the Roblox Studio MCP is connected to that exact Studio session.
- Use the target place for all subsequent operations.

## 4. Second Action: Ask for Modification Authorization

After the target place is identified, ask:

> "Do you authorize me to make the necessary VFX modifications in this place?"

- **If I say yes:** you may autonomously create, modify, test, and clean up the VFX-related objects and scripts necessary for the requested VFX work.
- **If I say no:** only inspect and report. Do not make modifications without authorization.

## 5. Environment Audit

Before doing actual VFX work, perform a lightweight audit. Check:

- Node.js
- npm
- npx
- Claude Code
- roblox-vfx
- Roblox Studio
- Roblox Studio MCP
- VFX Forge
- EmitModule
- shared.vfx

Do not reinstall things that already work. Do not update software simply because a newer version exists. Prioritize compatibility and stability. Report only relevant findings.

## 6. Node / npm / npx

Verify:

```
node --version
npm --version
npx --version
```

- If they work: leave them alone.
- If something is missing: install an appropriate stable/LTS version.
- Do not unnecessarily upgrade npm.
- After any installation, verify the commands again.

## 7. roblox-vfx Skill

Verify that the global Claude Code skill exists.

Expected location:

```
C:\Users\<USERNAME>\.claude\skills\roblox-vfx\
```

If it is missing, install it using:

```
npx skills add https://github.com/nonlooped/roblox-suite --skill roblox-vfx --global --agent claude-code
```

Then verify `SKILL.md`. Read the skill instructions before performing advanced VFX work.

**IMPORTANT:**
- The roblox-vfx skill is a knowledge layer. It is not Roblox Studio itself.
- Do not confuse the skill with the Roblox Studio MCP.
- If the skill was installed during an already-running Claude session and is not recognized, do not reinstall it repeatedly. Instead, tell me that a new Claude Code session may be required.

## 8. Roblox Studio MCP

Verify that the existing Roblox Studio MCP is available.

Expected MCP: `roblox-studio`

- Use the existing configuration whenever possible.
- Do not create duplicate MCP configurations.
- Do not install an alternative Roblox Studio MCP.
- If the existing launcher dynamically finds the current Roblox Studio installation, keep that architecture.
- Do not unnecessarily replace a working dynamic launcher with a hardcoded path.

## 9. MCP Connection

Verify the actual Studio connection. Use the available Roblox Studio MCP tools to identify:

- connected Studio sessions
- target place
- Studio state
- game tree

At minimum, verify that you can safely read the target Studio state. Do not perform destructive operations during this check.

If multiple Studio sessions exist: explicitly identify the target session before doing anything.

## 10. VFX Forge

Verify the local VFX Forge plugin.

Expected file:

```
C:\Users\<USERNAME>\AppData\Local\Roblox\Plugins\VFX.rbxmx
```

Expected version: **VFX Forge 1.4.5**

If it is already installed and working:
- DO NOT reinstall it.
- DO NOT modify the plugin file.
- DO NOT patch the plugin.
- DO NOT replace it with another copy unless I explicitly request it.

If it is missing: tell me that the official/local VFX Forge plugin needs to be provided or installed. Do not download random copies.

## 11. VFX Forge UI

Verify that VFX Forge is loaded in the TARGET Roblox Studio session. Verify the VFX Forge toolbar and its available controls.

If the plugin UI is disabled: use the plugin's normal UI mechanism to enable it. Do not modify the plugin's internal source. Do not patch the plugin.

## 12. Emit Module

Verify whether the TARGET PLACE contains `ReplicatedStorage.EmitModule`.

- If it already exists and is valid: use it. Do not recreate it. Do not replace it unnecessarily.
- If it does not exist: use the real VFX Forge workflow: **VFX Forge → Emit Module**.
- If the plugin requires manual interaction, ask me to perform that action.

**Licensing:**
- Never bypass a license or agreement.
- If VFX Forge displays a VFX-DL agreement, I must personally accept it. You must not accept it for me.
- After I accept it, verify `ReplicatedStorage.EmitModule` in the TARGET PLACE.

**IMPORTANT:** EmitModule is place-specific. Never assume that another place already contains it.

## 13. EmitModule Validation

Verify that `ReplicatedStorage.EmitModule` is a real ModuleScript generated by VFX Forge.

- Do not manually recreate the module.
- Do not rewrite it.
- Do not optimize it.
- Do not rename it unless I explicitly request it.
- When possible, verify compatibility with the installed VFX Forge version.

Expected: `VFX Forge 1.4.5 → lib/emit → EmitModule`

## 14. shared.vfx

Verify the runtime interface exposed by the VFX system. Where available, verify:

- `shared.vfx`
- `shared.vfx.init`
- `shared.vfx.deinit`
- `shared.vfx.emit`
- `shared.vfx.setup`
- `shared.vfx.scope`
- `shared.vfx.caches`

Do not assume every environment exposes every field identically. Inspect the actual runtime. Do not invent APIs.

## 15. Runtime Test

Before building complex VFX, perform a minimal runtime test if needed. The test should verify:

```
init
↓
emit
↓
effect completion
↓
cleanup
↓
deinit
↓
optional re-init
```

- Use a temporary normal game script in Play when appropriate.
- Respect the VFX Forge licensing restrictions.
- Do not bypass licensing restrictions using development tools.
- Do not create permanent test systems.

## 16. Test Cleanup

After any environment test:

- stop Play
- remove temporary scripts
- remove temporary Parts
- remove temporary effects
- remove temporary objects
- verify no unexpected leftovers
- inspect the console
- check warnings
- check errors

Do not save temporary test content unless explicitly required.

## 17. VFX Development Rules

When I request a VFX:

- First inspect the existing VFX structure.
- Then determine the correct implementation.
- Prefer the existing VFX Forge runtime where appropriate.
- Use the actual APIs exposed by the installed environment.
- Do not invent APIs.
- Do not create unnecessary systems.
- Do not duplicate existing effects unnecessarily.
- Keep VFX modular and reusable.

## 18. Visual Quality

When creating VFX, prioritize:

- strong silhouettes
- readable composition
- good timing
- controlled bursts
- layered effects
- impact
- motion
- lighting
- camera feedback when appropriate
- cleanup
- performance

For cinematic effects, use appropriate combinations of:

- ParticleEmitters
- Beams
- Trails
- Mesh effects
- shockwaves
- rings
- light flashes
- camera shake
- FOV effects
- camera motion
- temporary post-processing
- bursts
- trails
- debris
- energy streaks

Only use components that are actually appropriate for the requested effect.

## 19. Camera Effects

If the requested VFX involves cinematic camera work, camera effects must be handled locally. Use:

- camera shake
- FOV punch
- camera movement
- rapid angle changes
- cinematic positioning
- brief flashes
- controlled post-processing

Do not directly control every player's camera from the server. Do not create unnecessary server-side camera systems. Camera effects should recover cleanly after the VFX ends.

## 20. Performance

Use the roblox-vfx skill to evaluate performance when appropriate. Consider:

- particle rate
- burst amount
- lifetime
- texture cost
- transparency
- LightEmission
- LightInfluence
- Beam usage
- Trail usage
- distance
- cleanup
- pooling
- unnecessary Parts
- permanent emitters

Do not perform speculative optimization. Optimize based on actual requirements and observed behavior.

## 21. Play Testing

Every meaningful VFX implementation should be tested in Play. Verify:

- visual result
- timing
- emission
- camera behavior
- cleanup
- console
- warnings
- errors

Use screenshots or other available Studio inspection tools when they materially help evaluate the result.

Do not stop at "the code runs." The actual visual result matters.

## 22. Iteration

- If the VFX works technically but looks weak: iterate.
- If the camera movement is boring: improve it.
- If the timing is weak: improve it.
- If the effect is visually noisy: rebalance it.
- If the performance is unnecessarily heavy: optimize it.

Do not claim a high-quality result without actually testing it.

## 23. Source / Existing Project Code

If the target place already contains an existing VFX system: inspect it before changing it.

- Do not rewrite existing VFX architecture without a reason.
- Preserve working systems.
- If a requested VFX depends on an existing game system: identify the dependency first.
- Do not blindly import unrelated systems.

## 24. Safety / Scope

- Do not modify anything outside the target place unless explicitly necessary and authorized.
- Do not modify unrelated gameplay.
- Do not modify unrelated scripts.
- Do not modify unrelated assets.
- Do not modify the VFX Forge plugin itself.
- Do not modify the EmitModule source.
- Do not create unnecessary permanent infrastructure.

## 25. Saving

Do not save merely because a test ran. During experimentation: prefer reversible changes.

Before a final save, verify that:

- the requested VFX works
- the target place is correct
- no temporary test objects remain
- no unexpected scripts remain
- console has no new errors
- cleanup works

Only then save, and only if I have authorized modifications.

## 26. When You Need Me

Ask me only when you genuinely need a decision or manual action. Examples:

- Which Studio place should I use?
- Do you authorize modifications?
- VFX-DL requires you to accept the agreement.
- A required plugin installation must be performed manually.
- A design decision cannot reasonably be inferred.

Do not repeatedly ask for permission for every small implementation step after I have authorized the work.

## 27. Failure Handling

If something fails:

1. identify the exact failure
2. inspect the relevant component
3. determine the root cause
4. attempt a safe correction
5. retest
6. report the result

Do not hide failures. Do not fabricate PASS results. Do not replace a failed component with a fake implementation just to make the test pass.

## 28. Final Report

When the requested work is complete, report:

```
ENVIRONMENT
Node:
npm:
npx:
Claude Code:
roblox-vfx:
Roblox Studio:
Studio version:
Roblox Studio MCP:

VFX FORGE
Installed:
Version:
Toolbar:
UI:
Emit Module:
EmitModule:

RUNTIME
shared.vfx:
init:
emit:
cleanup:
deinit:

VFX WORK
Requested effect:
Created:
Modified:
Tested:

PLAY TEST
Visual:
Timing:
Camera:
Performance:
Cleanup:
Console:
Warnings:
Errors:

CHANGES
List only the relevant files and Roblox instances that were actually changed.
Do not claim something was changed if it was only inspected.
```

## 29. Success Condition

The environment can be considered operational when all of these are confirmed working:

```
Node/npm/npx
↓
Claude Code
↓
roblox-vfx
↓
Roblox Studio MCP
↓
target Studio session
↓
VFX Forge 1.4.5
↓
EmitModule
↓
shared.vfx
↓
runtime test
```

For a VFX task, additionally require:

```
requested VFX
↓
Play Test
↓
visual verification
↓
cleanup
↓
console verification
```

Do not declare success based only on code inspection.

## 30. Most Important Rule

- DO NOT assume.
- DO NOT invent.
- DO NOT install unnecessary components.
- DO NOT use unrelated tooling.
- DO NOT modify the wrong Studio window.
- DO NOT bypass VFX-DL licensing.
- DO NOT recreate VFX Forge.
- DO NOT fake EmitModule.
- DO NOT claim PASS without verification.

Ask me for the TARGET PLACE first.
Ask me for modification authorization second.
After those two answers, work autonomously and complete the VFX task end-to-end.
