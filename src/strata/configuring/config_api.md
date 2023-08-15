# Config API
You can configure Strata through an API which contains functions that are called from the Lua script. It consists of a main module called `strata` which exposes a bunch of helper functions which are used to configure different parts the compositor like key bindings and window rules. This page shows all the functions and options available.

- [`strata`](#strata)
    - [`cmd`](#1-cmd)
      - [`spawn`](#11-spawn)
    - [`set_config`](#2-set_config)
    - [`set_bindings`](#3-set_bindings)
    - [`set_rules`](#4-set_rules)

# `strata`
This is the main module which contains all helper functions and variables accessible to the user.

## 1. `cmd`

Contains commonly used commands.

### 1.1 `spawn`

This command is used to launch programs.

**Arguments**
  1. `command` - the command to execute.

**Usage**
```lua
local strata = require("strata")

strata.spawn("kitty --title Terminal")
```

## 2. `set_config`
Used to set the static configuration for the compositor.

**Arguments**
  1. `config` - Lua table

**Usage**
```lua
local strata = require("strata")

strata.set_config {
	autostart = {
		{ "kitty --title Terminal" },
	},
	general = {
		workspaces = 9,
		gaps_in = 8,
		gaps_out = 12,
		kb_repeat = { 500, 250 },
	},
	decorations = {
		border = {
			width = 2,
			active = "#FFF",
			inactive = "#131418",
			radius = 5,
		},
		window = {
			opacity = 0.9,
		},
		blur = {
			enabled = true,
			size = 2,
			passes = 3,
			optimize = true,
		},
		shadow = {
			enabled = true,
			size = 2,
			blur = 3,
			color = "#FFF",
		},
	},
	tiling = {
		layout = "dwindle",
	},
	animations = {
		enabled = true,
	},
	bindings = {
		{
			keys = { "CTRL", "SHIFT", "Q" },
			cmd = close_all_windows,
		},
		{
			keys = { "WIN", "RETURN" },
			cmd = strata.cmd.spawn("kitty --title Terminal"),
		},
		{
			keys = { "WIN", "SPACE" },
			cmd = strata.cmd.spawn("rofi --show drun"),
		},
	},
	rules = {
		{
			triggers = { { event = "win_open_pre", class_name = "firefox" } },
			action = function(window) window.send_to_workspace(1) end,
		},
		{
			triggers = {
				{ event = "win_open_pre", class_name = "mpv" },
				{ event = "win_open_pre", workspace = 1, class_name = "kitty" },
			},
			action = function(window) window.set_floating() end,
		},
	},
}
```

## 3. `set_bindings`
Used to set the key bindings for the compositor.

**Arguments**
  1. `bindings` - Lua table

**Usage**
```lua
local strata = require("strata")

strata.set_bindings {
	{
		keys = { "CTRL", "SHIFT", "Q" },
		cmd = close_all_windows,
	},
	{
		keys = { "WIN", "RETURN" },
		cmd = strata.cmd.spawn("kitty --title Terminal"),
	},
	{
		keys = { "WIN", "SPACE" },
		cmd = strata.cmd.spawn("rofi --show drun"),
	},
}
```

## 4. `set_rules`
Used to set the window rules for the compositor.

**Arguments**
  1. `rules` - Lua table

**Usage**
```lua
local strata = require("strata")

strata.set_rules {
	{
		triggers = { event = "win_open_pre", class_name = "firefox" },
		action = function(window) window.send_to_workspace(1) end,
	},
	{
		triggers = {
			{ event = "win_open_pre", class_name = "mpv" },
			{ event = "win_open_pre", workspace = 1, class_name = { "kitty", "wezterm" } },
		},
		action = function(window) window.set_floating() end,
	},

	strata.rules.bind_to_workspace(1, "firefox"),
	strata.rules.bind_to_workspace {
		{ 1, "firefox" },
		{ 2, "neovide" },
		{ 10, "slack" },
	},

	strata.rules.set_floating("mpv"),
}
```