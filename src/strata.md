# Strata

Strata is a cutting-edge, robust and sleek Wayland compositor written in [Rust](https://rust-lang.org) using the [Smithay](https://github.com/smithay/smithay) library. It is designed to be minimal and flexible yet customizable. It is configured in Lua which makes it possible to add custom functions and scripts. The ability to extend the compositor using plugins will be added in the near future.

## Some useful information

Strata is a **Wayland Compositor**, which is ***very*** different from an X11 Window Manager. Strata includes both a server and a client, whereas in an X11 window manager, the WM only comes with the client. The rest is done by the Xorg server.