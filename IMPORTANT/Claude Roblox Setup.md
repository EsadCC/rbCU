---
tags: [roblox, claude, setup, mcp, plugins]
type: setup-guide
---
# Claude Roblox Setup

Back to [[Roblox Dev Resources]]

These are tools that make Claude better for Roblox development.

> [!tip] Claude Desktop first
> Most install prompts below say **Claude Code**. Try each one in **Claude Desktop** first. If it does not work there, say so (for example: "this didn't work in Claude Desktop") and then run it in Claude Code.

> [!tip] Simple rule
> - 🧠 **Skills** = teach Claude how to do things
> - 🔌 **MCP** = lets Claude actually control apps like Roblox Studio or Blender
> - 📦 **Plugins** = install extra features into Claude

---

## 🧠 Agent Skills

**What it does:** Lets Claude use extra skills for specific jobs. Example: a Roblox building skill can teach Claude how you want maps built.

**Activation:** Usually automatic. Claude uses the skill when it matches what you're asking. You normally do NOT have to call it manually.

---

## 🕸️ Graphify

**What it does:** Helps Claude understand how your whole game is connected.

**Useful for:**
- Big Roblox games
- Lots of scripts
- Finding what connects to what
- Understanding old code

**Activation:** Run `/graphify`. Run it again after making big changes to your game.

**Download prompt:**

```
Install Graphify for Claude Code.

Use:

pip install graphifyy
graphify install

Do not remove any of my existing Claude settings, plugins, skills, or MCPs.

When finished:
- Verify Graphify installed correctly
- Verify /graphify works
- Tell me if I need to restart Claude Code
```

---

## 🐴 Ponytail

**What it does:** Stops Claude from making simple code way too complicated. It helps Claude write cleaner and simpler code instead of creating tons of unnecessary systems.

**Activation:** Automatic. You normally do NOT need to call it.

**Download prompt:**

```
Install Ponytail for Claude Code.

Use:

/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail

Do not remove any of my existing plugins, skills, MCPs, or settings.

When finished:
- Verify Ponytail is installed
- Tell me if I need to restart Claude Code
- Confirm that it activates automatically while coding
```

---

## 🎮 Roblox Dev

**What it does:** Makes Claude better at Roblox coding.

**Helps with:** Luau, DataStores, Remotes, Security, Performance, Client/server code

**Activation:** Automatic when you're working on Roblox.

**Download prompt:**

```
Install Roblox Dev for Claude Code.

Use:

/plugin marketplace add ivar-anon/roblox-dev
/plugin install roblox-dev@roblox-dev

Do not remove anything I already have installed.

When finished:
- Verify Roblox Dev is installed
- Tell me what Roblox features were added
- Confirm it activates automatically
```

---

## 🧰 Roblox Claude Skills

**What it does:** Adds different Roblox skills to Claude.

**Includes things like:** Map building, UI building, Debugging, Roblox API help, Code cleanup, Game setup

**Activation:** Mostly automatic. Examples:
- "Build me an arena" → Claude can use the map-building skill.
- "Create an inventory UI" → Claude can use the UI skill.

**Download prompt:**

```
Install the Claude skills from:

https://github.com/benhelland/roblox-claude-skills

Install:

rojo-sync
luau-lint
roblox-api
script-scaffold
world-builder
studio-debug
scene-architect
game-bootstrap
ui-builder

Install them into my Claude skills folder.

Do not delete or overwrite any skills I already have.

When finished:
- Verify every skill installed correctly
- Tell me which skills need Roblox Studio MCP
- Tell me if anything else needs to be installed
```

---

## 🏗️ Roblox Studio Skill

**What it does:** Makes Claude better at building inside Roblox Studio. Instead of instantly changing things, it tries to **Inspect → Plan → Build → Test**.

**Useful for:** Maps, Arenas, Object placement, Level design, Playtesting

**Activation:** Usually automatic when you're working in Studio.

**Download prompt:**

```
Install the Roblox Studio skill.

Use:

/plugin marketplace add ShiroKSH/skills
/plugin install roblox-studio@skills

Do not remove any existing plugins, skills, or MCPs.

After installing:
- Follow the required Roblox Studio setup
- Connect it to my open Roblox Studio
- Test the connection by inspecting Workspace
- Do not change anything in my game during the test
```

---

## 🔌 Roblox Studio MCP

**What it does:** Lets Claude actually see and edit your Roblox Studio game.

- Without MCP: Claude mostly gives you code.
- With MCP: Claude can work with the actual game.

**Activation:** Automatic once connected. You can just say things like "Inspect my game", "Fix this system", "Build this area", "Look at StarterGui".

**Download prompt:**

```
Set up Roblox Studio MCP for Claude Code.

Use:

claude mcp add robloxstudio -- npx -y robloxstudio-mcp@latest

Before installing:
- Check my current MCP setup
- Do not remove any existing MCPs
- Do not remove Blender MCP

After installing:
- Tell me if Roblox Studio needs a plugin
- Help me connect it
- Verify Claude can see Workspace
- Also check ReplicatedStorage, ServerScriptService, and StarterGui
- Do not edit anything during the connection test
```

---

## 🧪 Skill Creator

**What it does:** Lets you make your own Claude skills.

**Example custom skills:** Roblox map builder, Roblox UI style, Roblox VFX, Roblox animation importer, Roblox debugger

**Activation:** Ask Claude to create or improve a skill. Example: "Use Skill Creator to make me a Roblox building skill."

**Download prompt:**

```
Install Skill Creator.

Use:

/plugin install skill-creator@claude-plugins-official

Do not remove anything I already have installed.

When finished:
- Verify Skill Creator works
- Tell me where new skills are saved
- Confirm Claude can create and improve skills
```

---

## 🦸 Superpowers

**What it does:** Makes Claude plan more before working on big features.

**Useful for:** Big game systems, Complicated bugs, Large updates, Features that need testing. Probably unnecessary for tiny changes.

**Activation:** Usually automatic. You can also say "Use Superpowers for this."

**Download prompt:**

```
Install Superpowers.

Use:

/plugin install superpowers@claude-plugins-official

Do not remove any of my existing setup.

When finished:
- Verify it is installed
- Tell me if I need to restart Claude Code
- Explain when it activates automatically
```

---

## 🧊 Blender MCP

**What it does:** Lets Claude control Blender.

**Useful for making:** Swords, Enemies, Buildings, Props, Armor, Roblox 3D models

**Activation:** Automatic once connected. Just say "Use Blender to make this."

**Download prompt:**

```
Set up Blender MCP for Claude Code.

Use:

uvx blender-mcp

Before changing anything:
- Check my current MCP setup
- Keep Roblox Studio MCP
- Keep every other MCP I already have
- Add Blender instead of replacing anything

After setup:
- Verify Blender connects
- Tell me what Claude can control in Blender
- Do not change my Blender project during the connection test
```

---

## ⚡ Simple Summary

| Tool | What it does |
|---|---|
| 🧠 Agent Skills | Adds extra abilities to Claude |
| 🐴 Ponytail | Stops Claude from overcomplicating code |
| 🕸️ Graphify | Helps Claude understand your whole game |
| 🎮 Roblox Dev | Makes Claude better at Roblox coding |
| 🧰 Roblox Claude Skills | Adds Roblox building, UI, debugging, and other skills |
| 🏗️ Roblox Studio Skill | Makes Claude better at building and testing in Studio |
| 🔌 Roblox Studio MCP | Lets Claude actually control Roblox Studio |
| 🧪 Skill Creator | Lets you make your own Claude skills |
| 🦸 Superpowers | Helps Claude handle big coding jobs |
| 🧊 Blender MCP | Lets Claude control Blender |

Related: [[VFX One-Shot Session Bootstrap]], [[Build Rules]]
