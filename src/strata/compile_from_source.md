# Compiling from Source

## 1. Dependencies

To compile and use Strata, you need some dependencies which have to be installed using a package manager, such as `pacman` or `apt`, depending on your distro. The required dependencies are listed below:

* `udev`
* `wayland` 
* `wayland-protocols` 
* `libinput` 
* `libxkbcommon` 
* `libglvnd` 
* `seatd` 
* `dbus-glib `
* `mesa`

If you're on Arch or any Arch based distro (such as Artix, Garuda, Manjaro, etc), you can install these using the following command:

```sh
sudo pacman -S udev wayland wayland-protocols libinput libxkbcommon libglvnd seatd dbus-glib mesa
```

If you're on Debian, or Debian based distros such as Ubuntu, Mate, Zorin, etc... you can install these using this command:

```sh
sudo apt-get install libudev-dev libgbm-dev libxkbcommon-dev libegl1-mesa-dev libwayland-dev libinput-dev libdbus-1-dev libsystemd-dev libseat-dev
```

## 2. Installing Rust

To compile Strata, you have to install Rust:

### All Linux distros

```sh
curl https://sh.rustup.rs -sSf | sh
```

### Arch Linux

```sh
sudo pacman -S rust
```


## 3. Compiling
 ### 3.1 Clone the repository
 ```sh
 git clone https://github.com/stratawm/stratawm
 ```

 ### 3.2 Compile and Install
 To install, `cd` into the cloned repo and then run:
 ```sh
 cargo install --path .
 ```
 This'll install it for your user. If you want to install it globally (which is not recommended right now), then run:
 ```sh
 sudo cargo install --path .
 ```
You can sit back and relax while it installs Strata. It might take a bit of time since it has to compile the source code and all the dependencies but if your system is a bit better than a potato, this won't take much time.

 ## Next steps
 Congratulations! If all went well, you should have Strata installed on your system. The next chapter will teach you how to configure Strata.