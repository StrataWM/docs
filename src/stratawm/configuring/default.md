# Default Config
```toml
[autostart]
[[autostart.cmd]]
cmd = "kitty --title Terminal"

[[autostart.cmd]]
cmd = "kagi"

[general]
workspaces = 9
in_gaps = 4
out_gaps = 8
kb_repeat = [500, 250]

[window_decorations]
border_width = 2
border_active = "#FFF"
border_inactive = "#131418"
border_radius = 5
window_opacity = 0.9
blur_enable = true
blur_size = 2
blur_passes = 2
blur_optimization = true
shadows_enabled = true
shadow_size = 4
shadow_blur = 3
shadow_color = "#FFF"

[tiling]
layout = "binary_tree" # Available: binary_tree, master, stack

[animations]
anim_enabled = true

[rules]
[[rules.workspace]]
workspace = 1
class_name = "kitty"

[[rules.workspace]]
workspace = 2
class_name = "Brave-browser"

[[rules.workspace]]
workspace = 3
class_name = "Code"

[[rules.floating]]
class_name = "pavucontrol"
```