# Default Config

```lua
local strata = require("strata")

local function close_all_windows()
	for _, window in ipairs(strata.current_workspace:get_windows()) do
		window:close()
	end
end

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