# Possible Values

## `autostart`
**Description** - Programs that are to be started when launching Strata

**Values** - 
1. **`cmd`** - Command to be executed

**Example** -
```toml
[autostart]
[[autostart.cmd]]
cmd = "kagi"
```

## `general`
**Description** - General settings for Strata

**Values** -
1. **`workspaces`** - Number of total workspaces
2. **`in_gaps`** - Gaps between windows
3. **`out_gaps`** - Gaps outside window edges
4. **`kb_repeat`** - Repeat settings for keyboard in the form `[repeat_delay, repeat_rate]` where `repeat_delay` is the amount of time before the pressed key starts auto repeating (in ms) and `repeat_rate` is the delay between each repeat key press

**Default Values** -
```toml
[general]
workspaces = 9
in_gaps = 4
out_gaps = 8
kb_repeat = [500, 250]
```

## `window_decorations`
**Description** - Decorations for windows

**Values** - 
1. **`border_width`** - The width of the window border in pixels.
2. **`border_active`** - The color of the border when the window is active.
3. **`border_inactive`** - The color of the border when the window is inactive.
4. **`border_radius`** - The radius of the window corners in pixels.
5. **`window_opacity`** - The opacity of the window, ranging from 0.0 (completely transparent) to 1.0 (fully opaque).
6. **`blur_enable`** - A boolean value indicating whether window blur is enabled.
7. **`blur_size`** - The size of the window blur effect in pixels.
8. **`blur_passes`** - The number of blur passes to apply to the window. More the passes, more refined is the blur.
9.  **`blur_optimization`** - A boolean value indicating whether optimization is applied to the blur effect.
10. **`shadows_enabled`** - A boolean value indicating whether window shadows are enabled.
11. **`shadow_size`** - The size of the window shadow in pixels.
12. **`shadow_blur`** - The blur level of the window shadow.
13. **`shadow_color`** - The color of the window shadow.

**Default Values**-
```toml
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
```

## `tiling`
**Description** - Values for configuring the behaviour of tiling.

**Values** -
1. `layout` - The default layout to be used when tiling.

**Default Values**-
```toml
[tiling]
layout = "binary_tree"
```

## `animations`
**Description** - Values for configuring window animations

**Values** -
1. `anim_enabled` - Whether or not animations are enabled.

**Default Values**

```toml
[animations]
anim_enabled = true
```

## `rules`
**Description** - Window rules

**Values** -
1. `workspace` 
    - **Description** - Workspce rules. Defines which windows are to be moved to which workspaces

    - **Values** -
      1. `workspace` - The workspace ID
      2. `class_name` - The window name. 

2. `floating`
    - **Description** - Floating rules. Defines which windows should float by default.

    - **Values** -
      1. `class_name` - The window name.

**Default Values**
```toml
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