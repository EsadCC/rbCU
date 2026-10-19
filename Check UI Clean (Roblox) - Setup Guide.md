# Check UI Clean (Roblox) — Setup Guide

> Source: https://github.com/TemporaryLooker22/Check-UI-Clean-Roblox
> A clean, modern Roblox UI library — customizable notifications, HUD, and game UI with smooth animations. Built with Roblox Studio.

## What it is

A UI library for Roblox that gives you clean, modern looking interfaces:
- Customizable notifications
- HUD elements
- General game UI
- Smooth animations

**Language breakdown:** Lua 99.8%, CSS 0.2%
**Stars:** 9 · **Forks:** 1

---

## Quick Start (Test in 1 minute)

The fastest way to try it is with the demo script.

1. Open **Roblox Studio**
2. Create a new `LocalScript` inside **StarterPlayerScripts**
3. Paste this code:

```lua
--!strict

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local UI = require(ReplicatedStorage:WaitForChild("UI"))

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

UI:CreateNotification({
    Title = "Welcome!",
    Message = "Check UI loaded successfully.",
    Duration = 5,
    NotificationType = "Success",
})
```

4. Press **Play (F5)** — a notification appears in the top-right.

> Note: this assumes a `UI` module exists in `ReplicatedStorage`. The demo script in the repo (see below) handles placing it.

---

## Demo Script (UI Module)

The repo ships a `demo.lua` that **creates the full `UI` module** as a `ModuleScript` in `ReplicatedStorage`, with all its sub-modules. Structure it produces:

```
ReplicatedStorage
└── UI (ModuleScript)
    ├── Components
    │   ├── NotificationSystem
    │   └── HUD
    └── utils
        └── Tween
```

### How to use the demo

1. Create a **Script** in `ServerScriptService`
2. Paste the `demo.lua` content
3. Run the game — it builds the `UI` module automatically
4. Then use the Quick Start snippet to show a notification

---

## Manual Installation

Prefer doing it by hand? Create this structure in `ReplicatedStorage`:

```
ReplicatedStorage
└── UI (ModuleScript)
    ├── Components
    │   ├── NotificationSystem (ModuleScript)
    │   └── HUD (ModuleScript)
    └── utils
        └── Tween (ModuleScript)
```

Then copy the source from the repo's `src/` folder into each file:

- `src/init.lua` → main `UI` module
- `src/Components/NotificationSystem.lua`
- `src/Components/HUD.lua`
- `src/utils/Tween.lua`

---

## Notification API

```lua
UI:CreateNotification({
    Title = "string",             -- notification title
    Message = "string",           -- body text
    Duration = 5,                 -- seconds on screen
    NotificationType = "Success", -- Success / Error / Warning / Info
})
```

### Notification types

| Type | Use for |
|------|---------|
| `Success` | confirms a successful action |
| `Error` | something failed |
| `Warning` | caution / non-fatal |
| `Info` | neutral info |

---

## HUD API (basic)

```lua
local hud = UI:CreateHUD({
    Health = true,
    Money = true,
    CustomStats = {
        {Name = "Score", Value = 0, Icon = "🏆"},
    },
})
```

---

## Configuration

Edit the top of `src/init.lua`:

```lua
local CONFIG = {
    DefaultDuration = 5,           -- default notification duration (s)
    MaxNotifications = 5,          -- max visible at once
    AnimationSpeed = 0.3,          -- animation time (s)
    Position = "TopRight",         -- TopRight / TopLeft / BottomRight / BottomLeft
    Theme = "Dark",                -- Dark / Light
}
```

---

## Customization

### Themes

```lua
local Themes = {
    Dark = {
        Background = Color3.fromRGB(30, 30, 30),
        Text = Color3.fromRGB(255, 255, 255),
        Border = Color3.fromRGB(60, 60, 60),
    },
    Light = {
        Background = Color3.fromRGB(245, 245, 245),
        Text = Color3.fromRGB(30, 30, 30),
        Border = Color3.fromRGB(200, 200, 200),
    },
}
```

### Adding your own notification type

1. Open `src/Components/NotificationSystem.lua`
2. Find the `NotificationColors` table
3. Add your type:

```lua
local NotificationColors = {
    Success = Color3.fromRGB(46, 204, 113),
    Error   = Color3.fromRGB(231, 76, 60),
    Warning = Color3.fromRGB(241, 196, 15),
    Info    = Color3.fromRGB(52, 152, 219),
    Custom  = Color3.fromRGB(155, 89, 182), -- your new type
}
```

4. Use it: `UI:CreateNotification({ ... NotificationType = "Custom" })`

---

## Examples

```lua
-- Success
UI:CreateNotification({
    Title = "Purchase Complete",
    Message = "You bought 100 coins!",
    NotificationType = "Success",
})

-- Error
UI:CreateNotification({
    Title = "Insufficient Funds",
    Message = "You need 500 more coins.",
    NotificationType = "Error",
})

-- Queue many (respects MaxNotifications)
for i = 1, 5 do
    UI:CreateNotification({
        Title = "Notification " .. i,
        Message = "This is notification number " .. i,
        NotificationType = "Info",
    })
end
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| **UI module not found** | Make sure `UI` ModuleScript is in `ReplicatedStorage` and spelled exactly |
| **Notifications not showing** | Check PlayerGui exists; verify the script runs on the client (LocalScript) |
| **Animations stutter** | Lower `AnimationSpeed` or reduce `MaxNotifications` |

---

## Project Structure (repo)

```
Check-UI-Clean-Roblox/
├── README.md
├── demo.lua                 # creates the UI module automatically
├── src/
│   ├── init.lua             # main UI module
│   ├── Components/
│   │   ├── NotificationSystem.lua
│   │   └── HUD.lua
│   └── utils/
│       └── Tween.lua
└── LICENSE (MIT)
```

---

## Requirements

- Roblox Studio
- Basic Lua/Luau knowledge
- No external dependencies

---

## Links

- Repo: https://github.com/TemporaryLooker22/Check-UI-Clean-Roblox
- License: MIT (free to use, modify, distribute)

## Related notes

- [[Mining Empire - Project Memory]]
