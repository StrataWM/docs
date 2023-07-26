# StrataWM

Strata is a dynamic and sleek Wayland compositor and window manager for GNU/Linux systems. It's written completely in [Rust](https://rust-lang.org) using the [Smithay](https://github.com/smithay/smithay) library. Strata is made to be modular. It is done this way so that you, the user can mix N match different components to make Strata work the way you want. Strata follows this architecture, which is inspired by [BSPWM](https://github.com/baskerville/bspwm):

```txt
╭───────────────╮       ╭───────────╮       ╭──────────╮
│ Hotkey Daemon │ ────> │ StrataCTL │ ────> │ StrataWM │
╰───────────────╯       ╰───────────╯       ╰──────────╯
```

This makes it possible so that you can interchange components, for example, instead of using Kagi, the official Strata hotkey daemon, you can use [SWHKD](https://github.com/waycrate/swhkd) or even make your own. As Strata grows in complexity, this architecture will, hopefully, prove to be useful.